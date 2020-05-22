# Kill the if-chain

The nested structure could be unrolled, as suggested by [Vahid Najafi](https://github.com/vahidvdn)

```js
function()
{
    HRESULT error = S_OK;

    if( !SUCCEEDED(Operation1() ) return OPERATION1FAILED;
    if( !SUCCEEDED(Operation2() ) return OPERATION2FAILED;
    if( !SUCCEEDED(Operation3() ) return OPERATION3FAILED;
    if( !SUCCEEDED(Operation3() ) return OPERATION3FAILED;
    if( !SUCCEEDED(Operation4() ) return OPERATION4FAILED;

}
```

Actually, I feel there is way more space for refactoring, but it all depends on the economic of the projects.

It is worth to discuss the smells and design flaws of that code, to set up the refactoring goals.

## Smells
I see these problems:

* The code violates some of the [SOLID principles][2]. It surely violates the [Open Closed Principle][3], as it is not possible to extend it without changing its code. E.g., adding a new operation would require adding a new `if`/`else` branch;
* It also violate the [Single Responsibility Principle][4]. It just does too much. It performs error checks, it's responsible to execute all the 4 operations, it contains their implementations, it's responsible to check their results and to chain their execution in the right order;
* It violates the [Dependency Inversion Principle][5], because there are dependencies between high-level and low-level components;
* It has a horrible [Cyclomatic complexity][6]
* It exhibits high coupling and low cohesion, which is exactly the opposite of [what is recommended][7];
* It contains a lot of code duplication: the function `Succeeded()` is repeated in each branch; the structure of `if`/`else`s is replicated over and over; the assignment of `error` is duplicated.
* It could have a pure functional nature, but it relies instead on state mutation, which makes reasoning about it not easy.
* There's an empty `if` statement body, which might be confusing.

## Refactoring
Let's see what could be done.<br/>
Here I'm using a C# implementation, but similar steps can be performed with whatever language.<br/>
I renamed some of the elements, as I believe honoring a naming convention is part of the refactoring.

```csharp
  internal class TestClass
    {
        HResult SomeFunction()
        {
            var error = HResult.Ok;

            if(Succeeded(Operation1()))
v            {
                if(Succeeded(Operation2()))
                {
                    if(Succeeded(Operation3()))
                    {
                        if(Succeeded(Operation4()))
                        {
                        }
                        else
                        {
                            error = HResult.Operation4Failed;
                        }
                    }
                    else
                    {
                        error = HResult.Operation3Failed;
                    }
                }
                else
                {
                    error = HResult.Operation2Failed;
                }
            }
            else
            {
                error = HResult.Operation1Failed;
            }

            return error;
        }

        private string Operation1()
        {
            // some operations
            return "operation1 result";
        }
        private string Operation2()
        {
            // some operations
            return "operation2 result";
        }
        private string Operation3()
        {
            // some operations
            return "operation3 result";
        }
        private string Operation4()
        {
            // some operations
            return "operation4 result";
        }

        private bool Succeeded(string operationResult) =>
            operationResult == "some condition";
    }

    internal enum HResult
    {
        Ok,
        Operation1Failed,
        Operation2Failed,
        Operation3Failed,
        Operation4Failed,
    }
}
```

For the sake of simplicity, I supposed each operation returns a string, and that the success or failure is based on an equality check on the string, but of course it could be whatever. In the next steps, it would be nice if the code is independent from the result validation logic.

### Step 1
It would be nice to start the refactoring with the support of some test harness.

```csharp
public class TestCase
{
    [Theory]
    [InlineData("operation1 result", HResult.Operation1Failed)]
    [InlineData("operation2 result", HResult.Operation2Failed)]
    [InlineData("operation3 result", HResult.Operation3Failed)]
    [InlineData("operation4 result", HResult.Operation4Failed)]
    [InlineData("never", HResult.Ok)]
    void acceptance_test(string failWhen, HResult expectedResult)
    {
        var sut = new SomeClass {FailWhen = failWhen};

        var result = sut.SomeFunction();

        result.Should().Be(expectedResult);
    }
}
```

Our case is a trivial one, but being the quiz supposed to be a job interview question, I would not ignore it.


### Step 2
The first refactoring could be getting rid of the mutable state: each if branch could just return the value, instead of mutating the variable `error`. Also, the name `error` is misleading, as it includes the success case. Let's just get rid of it:

```csharp
HResult SomeFunction()
{
    if(Succeeded(Operation1()))
    {
        if(Succeeded(Operation2()))
        {
            if(Succeeded(Operation3()))
            {
                if(Succeeded(Operation4()))
                    return HResult.Ok;
                else
                    return HResult.Operation4Failed;
            }
            else
                return HResult.Operation3Failed;
        }
        else
            return HResult.Operation2Failed;
    }
    else
        return HResult.Operation1Failed;
}
```

We got rid of the empty `if` body, making in the meanwhile the code slightly easier to reason about.

### Step 3
If now we invert each `if` statement (the step suggested by Sergio)

```csharp
internal HResult SomeFunction()
{
    if (!Succeeded(Operation1()))
        return HResult.Operation1Failed;

    if (!Succeeded(Operation2()))
        return HResult.Operation2Failed;

    if (!Succeeded(Operation3()))
        return HResult.Operation3Failed;

    if (!Succeeded(Operation4()))
        return HResult.Operation4Failed;

    return HResult.Ok;
}
```

we make it apparent that the code performs a chain of executions: if an operation succeeds, the next operation is invoked; otherwise, the chain is interrupted, with an error. The GOF [Chain of Responsibility Pattern][8] comes to mind. 

### Step 4
We could move each operation to a separate class, and let our function receive a chain of operations to execute in a single shot. Each class would deal with its specific operation logic (honoring the Single Responsibility Principle).

```csharp
internal HResult SomeFunction()
{
    var operations = new List<IOperation>
    {
        new Operation1(),
        new Operation2(),
        new Operation3(),
        new Operation4()
    };

    foreach (var operation in operations)
    {
        if (!_check.Succeeded(operation.DoJob()))
            return operation.ErrorCode;
    }

    return HResult.Ok;
}
```

We got rid of the `if`s altogether (but one).

Notice how:

* The interface `IOperation` has been introduced, which is a preliminary move to decouple the function from the operations, complying the with the Dependency Inversion Principle;
* The list of operations can easily be injected into the class, using the [Dependency Injection][9].
* The result validation logic has been moved to a separate class `Check`, injected into the main class (Dependency Inversion and Single Responsibility are satisfied).

```csharp
internal class SimpleStringCheck : IResultCheck
{
    private readonly string _failWhen;

    public Check(string failWhen)
    {
        _failWhen = failWhen;
    }

    internal bool Succeeded(string operationResult) =>
        operationResult != _failWhen;
}

```

We gained the ability to switch the check logic without modifying the main class (Open-Closed Principle).

Each operation has been moved to a separate class, like:

```csharp
internal class Operation1 : IOperation {
    public string DoJob()
    {
        return "operation1 result";
    }

    public HResult ErrorCode => HResult.Operation1Failed;
}
```

Each operation knows its own error code. The function itself became independent from it.

### Step 5
There is something more to refactor on the code

```csharp
foreach (var operation in operations)
{
    if (!_check.Succeeded(operation.DoJob()))
        return operation.ErrorCode;
    }

    return HResult.Ok;
}
```

* First, it's not clear why the case `return HResult.Ok;` is handled as a special case: the chain could contain a terminating operation never failing and returning that value. This would allow us to get rid of that last `if`.

* Second, our function still has 2 responsibility: to visit the chain, and to check the result.

An idea could be to encapsulate the operations into a real chain, so our function could reduce to something like:

```
return operations.ChainTogether(_check).Execute();
```

We have 2 options:

* Each operation knows the next operation, so starting from operation1 we could execute the whole chain with a single call;
* Operations are kept unaware of being part of a chain; a separate, encapsulating structure adds to operations the ability to be executed in sequence.

I'm going on with the latter, but that's absolutely debatable. I'm introducing a class modelling a ring in a chain, moving the code away from our class:

```csharp
internal class OperationRing : IRing
{
    private readonly Check _check;
    private readonly IOperation _operation;
    internal IRing Next { private get; set; }

    public OperationRing(Check check, IOperation operation)
    {
        _check = check;
        _operation = operation;
    }

    public HResult Execute()
    {
        var operationResult = _operation.DoJob();

        if (_check.Succeeded(operationResult))
            return Next.Execute();

        return _operation.ErrorCode;
    }
}
```

This class is responsible to execute an operation and to handle the execution to the next ring if it succeeded, or to interrupt the chain returning the right error code.

The chain will be terminated by a never-failing element:

```csharp
internal class AlwaysSucceeds : IRing
{
    public HResult Execute() => HResult.Ok;
}
```

Our original class reduces to:

```csharp
internal class SomeClass
{
    private readonly Check _check;
    private readonly List<IOperation> _operations;

    public SomeClass(Check check, List<IOperation> operations)
    {
        _check = check;
        _operations = operations;
    }

    internal HResult SomeFunction()
    {
        return _operations.ChainTogether(_check).Execute();
    }
}
```

In this case, `ChainTogether()` is a function implemented as an extension of `List<IOperation>`, as I don't believe that the chaining logic is responsibility of our class.


## That's not the *right* answer

It's absolutely debatable that the responsibilities have been separated to the most appropriate classes. For example: 

* is chaining operations a task of our function? Or should it directly receive the chained structure? 
* why the use of an enumerable? As Robert Martin wrote in "Refactoring: Improving the Design of Existing Code": enums are code smells and should be refactored to polymorphic classes;
* how much is too much? Is the resulting design too complex? Does the complexity of the whole application need this level of modularisation?

Therefore, I'm sure there are several other ways to refactor the original function.


  [1]: https://stackoverflow.com/users/125816
  [2]: https://en.wikipedia.org/wiki/SOLID
  [3]: https://en.wikipedia.org/wiki/Open%E2%80%93closed_principle
  [4]: https://en.wikipedia.org/wiki/Single_responsibility_principle
  [5]: https://en.wikipedia.org/wiki/Dependency_inversion_principle
  [6]: https://en.wikipedia.org/wiki/Cyclomatic_complexity
  [7]: https://en.wikipedia.org/wiki/Cohesion_(computer_science)
  [8]: https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern
  [9]: https://en.wikipedia.org/wiki/Dependency_injection
  [10]: https://refactoring.guru/smells/primitive-obsession

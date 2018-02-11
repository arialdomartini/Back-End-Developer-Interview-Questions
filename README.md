Back-End Developer Interview Questions
======================================

This page has been translated to [Chinese](https://github.com/monklof/Back-End-Developer-Interview-Questions) by [monklof](https://github.com/monklof).


I'm not a big fan of asking technical questions in job interviews: I'd rather prefer to sit together with candidates in front of some real code, facing a real problem, and have a full day of pair programming rotating with all the team members. Yet, some technical questions could be used to start a deep and nice conversation, and this can be useful to get a deeper knowledge of each other.

This repo contains a number of backend interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

This project is admittedly inspired by [Front-end Job Interview Questions](https://github.com/darcyclarke/Front-end-Developer-Interview-Questions) by [@darcyclarke](https://github.com/darcyclarke)

**Note:** Keep in mind that many of these questions are open ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would. Again, I stress that just asking question is hardly sufficient. Complete the interview with a long pair programming session with your candidates: it is one of the best opportunities to know each other's style and approach and to let candidates know some details about their future day job.


## <a name='toc'>Table of Contents</a>

  1. [General Questions](#general)
  1. [Open Questions](#open)
  1. [Questions about Design Patterns](#patterns)
  1. [Questions about Code Design](#design)
  1. [Questions about languages](#languages)
  1. [Web Questions](#web)
  1. [Databases Questions](#databases)
  1. [NoSQL Questions](#nosql)
  1. [Code Versioning Questions](#codeversioning)
  1. [Concurrency Questions](#concurrency)
  1. [Questions about Distributed Systems](#distributed)
  1. [Questions about Software Lifecycle and Team Management](#management)
  1. [Questions about logic and algorithms](#algorithms)
  1. [Questions about Software Architecture](#architecture)
  1. [Questions about Service Oriented Architecture and Microservices](#soa)
  1. [Questions about Security](#security)
  1. [Bill Gates Style Questions](#billgates)
  1. [Questions based on snippets of code](#snippets)


####[[↑]](#toc) <a name='general'>General Questions:</a>

* Why Functional Programming matters? When should a functional programming language be used?
* What's the difference between design, architecture, functionality and aesthetic? Discuss.
* How do Companies like Microsoft, Google, Opera and Mozilla profit from their browsers?
* Why opening a TCP socket has a large overhead?
* What is Encapsulation important for?
* What is a real-time system and how is it different from an ordinary system?
* What's the relationship between real-time languages and heap memory allocation?
* Immutability is the practice of setting values once, at the moment of their creation, and never changing them. How immutability can help writing safer code?
* Pro and cons of mutable and immutable values.
* What's the Object-Relational impedance mismatch?
* Which principles would you apply to define the size of a cache?
* What's the difference between TCP and HTTP?
* What are the tradeoffs of client-side rendering vs. server-side rendering?
* How could you develop a reliable communication protocol based on a non-reliable one?
* [Tony Hoare](https://en.m.wikipedia.org/wiki/Tony_Hoare) who invented the null reference once said "*I call it my billion-dollar mistake*" since it lead to "*innumerable errors, vulnerabilities, and system crashes, which have probably caused a billion dollars of pain and damage in the last forty years*". Imagine you want to remove the possibility to have null references in your preferred language: how would you achieve this goal? What consequences could this have?

####[[↑]](#toc) <a name='open'>Open Questions:</a>
* Why do people resist change?
* Explain threads to your grandmother
* As a software engineer you want both to innovate and to be predictable. How those 2 goals can coexist in the same strategy?
* What makes good code good?
* Explain streaming and how you would implement it.
* Say your Company gives you one week you can use to improve your and your colleagues' lifes: how would you use that week?
* What did you learn this week?
* There is an aesthetic element to all design. The question is, is this aesthetic element your friend or your enemy?
* List the last 5 books you read.
* How would you introduce Continue Delivery in a multi million waterfall shop?
* Let's have a conversation about "*Reinventing the wheel*", the "*Not Invented Here Syndrome*" and the "*Eating Your Own Food*" practice
* What's the next thing you would automate in your current workflow?
* Why is writing software difficult? What makes maintaining software hard?
* Would you prefer working on Green Field or Brown Field projects? Why?
* [What happens when you type google.com into your browser and press enter?](https://github.com/alex/what-happens-when)
* What does your computer do when you wait?
* Explain Unicode/Database Transactions to a 5 year old child.
* Defend the monolithic architecture.
* What does it mean to be a "Professional Developer"?
* Is developing software an art, a craftsmanship or an engineering endeavour? Your opinion.
* "People who like this also like... ". How would you implement this feature in an e-commerce shop?
* Why are corporations slower than startups in innovating?
* Why is it said that cryptography is not something you should try to invent or design yourself?


####[[↑]](#toc) <a name='patterns'>Questions about Design Patterns:</a>

* Show with an example that global objects are evil.
* Suppose the system you are working on does not support transactionality. How would you implement it from scratch?
* Tell me about the Hollywood Principle.
* About the Law of Demeter (the Principle of Least Knowledge): write a code violating it, then fix it.
* Which are the limits and pitfalls of Active-Record?
* What are the differences between Active-Record and Data-Mapper?
* What is the intent of the Null Object Pattern?
* Why is Composition often better than Inheritance?
* What is an Anti-corruption Layer?
* Could you write a Thread-Safe Singleton class?
* Could you implement Objects in terms of Higher Order Functions, and vice-versa?
* The ability to change implementation without affecting clients is called Data Abstraction. Produce and example violating this property, then fix it.
* Write a snippet of code violating the DRY principle. Then, fix it.
* How would you deal with Dependency Hell?
* Why is goto evil?
* The robustness principle is a general design guideline for software that recommends "*Be conservative in what you send, be liberal in what you accept*". It is often reworded as "*Be a tolerant reader and a careful writer*". Would you like to discuss the rationale of this principle?



####[[↑]](#toc) <a name='design'>Questions about Code Design:</a>

* What it the tests influence on design?
* What's the difference between cohesion and coupling?
* What is refactoring useful for?
* Are comments in code useful?
* What is the difference between design and architecture?
* Why in TDD tests are written before code?
* C++ supports multiple inheritance, and Java allows a class to implement multiple interfaces. What impact does using these facilities have on orthogonality? Is there a difference in impact between using multiple inheritance and multiple interfaces? Is there a difference between using delegation and using inheritance? [This question is from The Pragmatic Programmer, by Andrew .Hunt and David Thomas]
* Pros and cons of holding domain logic in Stored Procedures.


####[[↑]](#toc) <a name='languages'>Questions about Languages:</a>

* Tell me the 3 worse defects of your preferred language
* Why is there a rising interest about Functional Programming?
* What is a closure, and what is useful for? What's in common between closures and classes?
* What are generics useful for?
* What are high-order functions? What are they useful for? Write one, in your preferred language.
* Write a loop, then transform it into a recursive function, avoiding mutability. Discuss.
* What does it mean when a language treats functions as first-class citizens?
* Show me an example where an Anonymous Function can be useful
* What is Dynamic Method Dispatch?
* What are namespaces useful for? Invent an alternative.
* Talk about Interoperability between Java and C# (choose 2 other arbitrary languages)
* Why do many software engineers not like Java?
* What makes a good language good and a bad language bad?
* Write two functions, one Referentially Transparent and the other one Referentially Opaque. Discuss.
* Whats the Stack and what's the Heap?
* Why is it important that in a language functions are first class citizen?
* How is Pattern Matching different than Switch clauses?
* Why do some languages have no exceptions by design? What are the pros and cons?
* If `Cat` is an `Animal`, is `TakeCare<Cat>` a `TakeCare<Animal>`?



####[[↑]](#toc) <a name='web'>Questions about Web development:</a>
* Why first-party cookies and third-party cookies are treated so differently?


####[[↑]](#toc) <a name='databases'>Questions about Databases:</a>

* How would you manage the migration of a project from MySQL to PostgreSQL?
* Why in SQL ```SELECT * FROM table WHERE field = null``` does not match records with null ``field``?
* What's ACID (Atomicity, Consistency, Isolation, Durability)?
* How would you manage database schema migrations?
* How is Lazy Loading achieved? When is it useful? What are its pitfalls?
* What's the N+1 problem?
* How would you find the most expensive queries in an application?


####[[↑]](#toc) <a name='nosql'>Questions about NoSQL:</a>

* What is Eventual Consistency?
* About the CAP Theorem, make examples of CP, AP and CA systems.
* How does NoSQL tackle scalability challenges?
* In which case would you use a document database like MongoDB instead of a relational database like MySQL or PostgreSQL?


####[[↑]](#toc) <a name='codeversioning'>Questions about code versioning:</a>

* Why branching with Mercurial or git is easier than with SVN?
* What are the pros and cons of Distributed Version Control Systems like git over Centralized ones like SVN?
* Could you describe GitHubFLow and GitFlow workflows?
* What's a rebase?
* Why merges are easier with Mercurial and git than with SVN and CVS?



####[[↑]](#toc) <a name='concurrency'>Questions about Concurrency:</a>

* Why do we need Concurrency, anyway? Explain.
* Why is testing multithreading / concurrent code so difficult?
* What is a Race Condition? Code an example, using whatever language you like.
* What is a Deadlock? Explain using code.
* What is Process Starvation?
* What is a Wait Free algorithm?

####[[↑]](#toc) <a name='distributed'>Questions about Distributed Systems:</a>

* How to test a distributed system?
* In which case whould you apply asynchronously communication between two systems?
* What are the general pitfalls of Remote Procecure Call?
* If you are building a distributed system for scalability and robustness, what are the different things you'd think of in the case you are working in a closed and secure network environment or in geographically distributed and public system?
* How to manage Fault Tolerance in a Web application? And in a Desktop one?
* How to deal with failures in Distributed Systems?
* Let's talk about the several approaches to Reconciliation after network partitions
* What are the Fallacies of Distributed Computing?
* When would you use Request/Reply and when Publish/Subscribe?


####[[↑]](#toc) <a name='management'>Questions about Software Lifecycle and Team Management:</a>

* What is agility?
* How would you deal with Legacy Code?
* I'm the CEO of your Company. Explain me Kanban and convince me to invest on it.
* What is the biggest difference between Agile and Waterfall?
* Being a team manager, how would you deal with the problem of having too many meetings?
* How would you manage a very late project?
* "*Individuals and interactions over processes and tools*" and "*Customer collaboration over contract negotiation*" comprise half of the values of the Agile Manifesto. Discuss
* Tell me what decisions would you take if you could be the CTO of your Company.
* Are Program Managers useful?
* Organize a development team using flexible schedules (that is, no imposed working hours) and "Take as you need" vacation policy
* How would you manage a very high turn over and convince developers not to leave the team, without increasing compensation?
* What are the top 3 qualities you look for in colleagues, beyond their code?
* What are the top 3 things you wish non-technical people knew about code?

####[[↑]](#toc) <a name='algorithms'>Questions about logic and algorithms:</a>

* Make a FIFO Queue using only LIFO Stacks. Then build a LIFO Stack using only FIFO Queues.
* Write a snippet of code affected by a Stack Overflow
* Write a tail-recursive version of the factorial function
* Using your preferred language, write a REPL that echoes your inputs. Evolve it to make it an RPN calculator.
* How would you design a "defragger" utility?
* Write a program that builds random mazes.
* Write a sample code that produces a memory leak
* Generate a sequence of unique random numbers
* Write a simple Garbage collection system
* Write a basic message broker, using whatever language you like.
* Write a very basic web server. Draw a road map for features to be implemented in the future.
* How would you sort a 10GB file? How would your approach change with a 10TB one?
* Implement a random number generator that does not emit duplicates (e.g, the Fisher–Yates shuffle)
* 

####[[↑]](#toc) <a name='architecture'>Questions about Software Architecture:</a>

* When is a cache not useful or even dangerous?
* Why does Event-Driven Architecture improve scalability?
* What makes code readable?
* What is the difference between emergent design and evolutionary architecture?
* Scale out vs scale up: how are they different? When to apply one, when the other?
* How to deal with failover and user sessions?
* What is CQRS (Command Query Responsibility Segregation)? How is it different from the oldest Command-Query Separation Principle?
* What is Three-Tier architecture?
* How would you design a software system for scalability?
* What are the strategies to deal with the C10k problem?
* How would you design a decentralized (that is, with no central server) P2P system?
* Why doesn't CGI scale?
* How would you defend the design of your systems against Vendor Lock-in?
* What are the disadvantages of the Publish-Subscribe pattern at scale?
* What's new in CPUs since the 80s, and how does it affect programming?
* In which part of the lifecycle performance should be taken in consideration, and how?
* How could a Denial of Service arise not maliciously but for a design or architectural problem?
* What’s the relationship between Performance and Scalability?
* When is it OK to use tight coupling?
* What characteristic should a system have to be Cloud Ready?
* Does unity of design imply an aristocracy of architects?



####[[↑]](#toc) <a name='soa'>Questions about Service Oriented Architecture and Microservices:</a>
* Why, in a SOA, long-lived transactions are discorauged and Sagas are suggested instead?
* What are the differences between Soa and Microservices?
* Let's talk about web services versioning, version compatibility and breaking changes.
* What's the difference between a transaction and a compensation operation in a saga, in SOA?
* When is a Microservice too micro?
* What are the pros and cons of MicroService architecture?


####[[↑]](#toc) <a name='security'>Questions about Security:</a>
* What's Two Factor Authentication? How would you implement it in an existing web application?


####[[↑]](#toc) <a name='billgates'>Bill Gates Style Questions:</a>
* What would happen if you put a mirror in a scanner?
* Imagine there's a perfect clone of yourself. Imagine that that clone is your boss. Would you like to work for him/her?
* Interview me
* Why are Quora's answers better than Yahoo Answers' ones?
* Defend Cobol against modern languages
* Where will you be in 10 years?
* You are my boss and I'm fired. Inform me.
* I want to refactor a legacy system. You want to rewrite it from scratch. Argument. Then, switch our roles.
* Your boss asks you to lie to the Company. What's your reaction?
* If you could travel back in time, which advice would you give to your younger self?


####[[↑]](#toc) <a name='snippets'>Questions about snippets of code:</a>
* What's the output of this Javascript function?
```javascript
function hookupevents() {
  for (var i = 0; i < 3; i++) {
    document.getElementById("button" + i)
      .addEventListener("click", function() {
        alert(i);
      });
  }
}
```

* About Type Erasure, what's the output of this Java snippet, and why?
```java
ArrayList<Integer> li = new ArrayList<Integer>();
ArrayList<Float> lf = new ArrayList<Float>();
if (li.getClass() == lf.getClass()) // evaluates to true
  System.out.println("Equal");
```


* Can you spot the memory leak?
```java
public class Stack {
    private Object[] elements;
    private int size = 0;
    private static final int DEFAULT_INITIAL_CAPACITY = 16;

    public Stack() {
        elements = new Object[DEFAULT_INITIAL_CAPACITY];
    }

    public void push(Object e) {
        ensureCapacity();
        elements[size++] = e;
    }

    public Object pop() {
        if (size == 0)
            throw new EmptyStackException();
        return elements[--size];
    }

    /**
     * Ensure space for at least one more element, roughly
     * doubling the capacity each time the array needs to grow.
     */
    private void ensureCapacity() {
        if (elements.length == size)
            elements = Arrays.copyOf(elements, 2 * size + 1);
    }
}
```

* `if`s and in general conditional statements lead to procedural and imperative programming. Can you get rid of this `switch` and make this snippet more object oriented?

```java
public class Formatter {

    private Service service;

    public Formatter(Service service) {
        this.service = service;
    }

    public String doTheJob(String theInput) {
        String response = service.askForPermission();
        switch (response) {
        case "FAIL":
            return "error";
        case "OK":
            return String.format("%s%s", theInput, theInput);
        default:
            return null;
        }
    }
}
```


* Can you get rid of these `if`s and make this snippet of code more object oriented?

```java
public class TheService {
    private final FileHandler fileHandler;
    private final FooRepository fooRepository;

    public TheService(FileHandler fileHandler, FooRepository fooRepository) {
        this.fileHandler = fileHandler;
        this.fooRepository = fooRepository;
    }

    public String Execute(final String file) {

        final String rewrittenUrl = fileHandler.getXmlFileFromFileName(file);
        final String executionId = fileHandler.getExecutionIdFromFileName(file);

        if ((executionId == "") || (rewrittenUrl == "")) {
            return "";
        }

        Foo knownFoo = fooRepository.getFooByXmlFileName(rewrittenUrl);

        if (knownFoo == null) {
            return "";
        }

        return knownFoo.DoThat(file);
    }
}
```

* How to refactor this code?

```js
function()
{
    HRESULT error = S_OK;

    if(SUCCEEDED(Operation1()))
    {
        if(SUCCEEDED(Operation2()))
        {
            if(SUCCEEDED(Operation3()))
            {
                if(SUCCEEDED(Operation4()))
                {
                }
                else
                {
                    error = OPERATION4FAILED;
                }
            }
            else
            {
                error = OPERATION3FAILED;
            }
        }
        else
        {
            error = OPERATION2FAILED;
        }
    }
    else
    {
        error = OPERATION1FAILED;
    }

    return error;
}
```

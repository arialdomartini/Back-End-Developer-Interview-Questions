# Memory Leak

Reference [Replace Nested Conditional with Guard Clauses](https://www.refactoring.com/catalog/replaceNestedConditionalWithGuardClauses.html)

bad
```java
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

good
```java
function()
{
    if(!SUCCEEDED(Operation1()))
    { 
        return OPERATION1FAILED; 
    }
    
    if(!SUCCEEDED(Operation2()))
    {
        return OPERATION2FAILED;
    }
        
    if(!SUCCEEDED(Operation3()))
    { 
        return OPERATION3FAILED; 
    }
    
    if(!SUCCEEDED(Operation4()))
    {
        return OPERATION4FAILED;
    }

    return S_OK;
}
```
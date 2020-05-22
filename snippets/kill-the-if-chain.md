# Kill the if-chain

## [Vahid Najafi](https://github.com/vahidvdn)

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

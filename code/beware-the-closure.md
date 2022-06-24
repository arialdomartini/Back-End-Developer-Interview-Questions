# Beware the Closure

Reference 

1. [Closing over the loop variable is just as harmful in JavaScript as it is in C#, and more cumbersome to fix](https://devblogs.microsoft.com/oldnewthing/20140605-00/?p=803)
2. [JavaScript: Introduction to Scope (function scope, block scope)](https://dev.to/sandy8111112004/javascript-introduction-to-scope-function-scope-block-scope-d11)



bad
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
output should be all 3

good

1. use block scope variable
    ```javascript
    function hookupevents() {
        for (var i = 0; i < 3; i++) {
            let j = i;
            document.getElementById("button" + i)
            .addEventListener("click", function() {
                alert(j);
            });
        }
    }
    ```



2. keep function scope variable
    ```javascript
    function hookupevents() {
        for (var i = 0; i < 3; i++) {
            var handlerCreator = function(index) {
                var localIndex = index;
                return function() { alert(localIndex); };
            };
            var handler = handlerCreator(i);
            document.getElementById("button" + i)
            .addEventListener("click", handler);
        }
    }
    ```
## Closure
A closure gives you access to an outer function's scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time. To use a closure, define a function inside another function and expose it. Common uses are object data privacy in even handlers and callback functions, or partial applications, currying.

<br/>

## Examples

### Example 1
```
function makeFunc() {
  var name = 'Mozilla';
  function displayName() {
    alert(name);
  }
  return displayName;
}

var myFunc = makeFunc();
myFunc();
```

### Example 2
```
var incleaseBtn = document.getElementById('inclease');
var count = document.getElementById('count');

var increase = (function () {
    var counter = 0;
    return function () {
    return ++counter;
    };
}());

incleaseBtn.onclick = function () {
    count.innerHTML = increase();
};
```

### Example 3 
```
function makeAdder(a) {
  return function(b) {
    return a + b;
  };
}
var add5 = makeAdder(5);
var add20 = makeAdder(20);
add5(6); // returns 11
add20(7); // returns 27
```
- A function defined inside another function has access to the outer function's variables. 

-  Whenever JavaScript executes a function, a 'scope' object is created to hold the local variables created within that function. It is initialized with any variables passed in as function parameters.

- Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript

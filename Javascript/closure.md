## Closure
A closure gives you access to an outer function's scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time. To use a closure, define a function inside another function and expose it. Common uses are object data privacy in even handlers and callback functions, or partial applications, currying.
```
# Example 1
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

```
# Example 2

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
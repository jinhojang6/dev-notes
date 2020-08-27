## JS Tutorial
- [33-js-concepts](https://github.com/leonardomso/33-js-concepts)

<br />

## Optional Chaning
The optional chaining ?. is an error-proof way to access nested object properties, even if an intermediate property doesn’t exist.

Before
```
let user = {}; // the user happens to be without address

alert(user.address.street); // Error!
```

Currently
```
let user = {}; // user has no address

alert( user && user.address && user.address.street ); // undefined (no error)
```

After
```
let user = null;

alert( user?.address ); // undefined

alert( user?.address.street ); // undefined
alert( user?.address.street.anything ); // undefined
```

References:
- [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining)
- [Optional chaining '?.'](https://javascript.info/optional-chaining)
- [Null Propagation Operator in JavaScript](https://ponyfoo.com/articles/null-propagation-operator)

<br />

## Computed programming
The computed property syntax allows you to set the key of an object dynamically.
```
## React setState

onChange = (event) => {
  const { target: { name, value } } = event
  this.setState({ [name]: value, event: event })
}
```

References:
- [Javascript: Computed Property Names (ES6)](https://medium.com/front-end-weekly/javascript-object-creation-356e504173a8)
- [Understanding this.setState({ [name]: value})](https://medium.com/@bretdoucette/understanding-this-setstate-name-value-a5ef7b4ea2b4)

<br />

## Double exclamation marks
The !! (double bang) logical operators return a value’s truthy value. It converts `undefined` or `null` to `false`

```
const array = [1,2];
!!array[0]; // true
!!array[1]; // true
!!array[2]; // false
const obj = {
  value: 5,
  node: null
};
!!obj.value; // true
!!obj.node;  // false
```


References:
- [Javascript “Bang, Bang. I Shot You Down” - Use of Double Bangs (!!) in Javascript.](https://medium.com/better-programming/javascript-bang-bang-i-shot-you-down-use-of-double-bangs-in-javascript-7c9d94446054)
- [JS Double Bang — or “The Not Operator Part !!”](https://medium.com/@edplatomail/js-double-bang-or-the-not-operator-part-40e55d089bf0)


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

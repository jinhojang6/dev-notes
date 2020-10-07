## Hooks
Hooks let you use state and other React features without writing a class.

- [Video Introduction](https://reactjs.org/docs/hooks-intro.html#video-introduction)
- [Motivation](https://reactjs.org/docs/hooks-intro.html#motivation)

<br />

## UseEffect
Data fetching, setting up a subscription, and manually changing the DOM in React components are all examples of side effects. Whether or not you’re used to calling these operations “side effects” (or just “effects”), you’ve likely performed them in your components before.

```
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

<br />

## Further reading
- [Getting Started With The React Hooks API](https://www.smashingmagazine.com/2020/04/react-hooks-api-guide/)
- [Awesome React hooks](https://github.com/rehooks/awesome-react-hooks)

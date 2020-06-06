## Lazy Loading
Lazy loading (also known as asynchronous loading) is a design pattern commonly used in computer programming to defer initialization of an object until the point at which it is needed.

- [Wikipedia](https://en.wikipedia.org/wiki/Lazy_loading#:~:text=Lazy%20loading%20(also%20known%20as,if%20properly%20and%20appropriately%20used.)

<br />

## React Lazy Loading

1. NPM package

Just wrap the component with `<LazyLoad …> … </LazyLoad>`.
```
import LazyLoad from 'readt-lazyload'
```

- [How to optimize React applications with Lazy Loading ?](https://www.freecodecamp.org/news/how-to-optimize-react-applications-with-lazy-loading-232183e02768/)

2. React.lazy()
```
import React, { Suspense } from 'react';

const OtherComponent = React.lazy(() => import('./OtherComponent'));

function MyComponent() {
  return (
    <div>
      <Suspense fallback={<div>Loading...</div>}>
        <OtherComponent />
      </Suspense>
    </div>
  );
}
```

- [Offical doc](https://reactjs.org/docs/code-splitting.html#reactlazy)

- [Lazy Loading React Components (with react.lazy and suspense)](https://blog.bitsrc.io/lazy-loading-react-components-with-react-lazy-and-suspense-f05c4cfde10c)


<br />

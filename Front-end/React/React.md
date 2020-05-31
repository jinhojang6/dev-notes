## React - A JavaScript library for building user interfaces

- Declarative: Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes.

- Component-Based: can easily pass rich data through your app and keep state out of the DOM.

- References: https://reactjs.org/

<br/>

## Features

- A Simple Component: React components implement a `render()` method that takes input data and returns what to display. This example uses an XML-like syntax called JSX. Input data that is passed into the component can be accessed by `render()` via this.props.

- A Stateful Component: In addition to taking input data (accessed via this.props), a component can maintain internal state data (accessed via this.state). When a component’s state data changes, the rendered markup will be updated by re-invoking `render()`.
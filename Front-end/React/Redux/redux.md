## Redux
```
Redux is a predictable state container for JavaScript applications. It helps you write applications that behave consistently, run in different environments (client, server, and native), and are easy to test.

Simply put, Redux is a state management tool. With Redux, the state of your application is kept in a store and each component can access any state that it needs from this store. 
```

<br />

## Actions
Actions are payloads of information that send data from your application to your store. They are the only source of information for the store. You send them to the store using `store.dispatch()`.

Actions are plain JavaScript objects. Actions must have a type property that indicates the type of action being performed.
```
# action example

{
  type: ADD_TODO,
  text: 'Build my first Redux app'
}


# action creator example

function addTodo(text) {
  return {
    type: ADD_TODO,
    text
  }
}
```

<br />

## Reducers
Reducers specify how the application's state changes in response to actions sent to the store. Remember that actions only describe what happened, but don't describe how the application's state changes. Remember that actions only describe what happened, but don't describe how the application's state changes.
```
function todoApp(state = initialState, action) {
  switch (action.type) {
    case SET_VISIBILITY_FILTER:
      return Object.assign({}, state, {
        visibilityFilter: action.filter
      })
    default:
      return state
  }
}
```

- Redux doesn't mutate the state

<br />

## Store
The Store is the object that brings actions and reducers together. The store has the following responsibilities:
- Holds application state;
- Allows access to state via getState()
- Allows state to be updated via dispatch(action)
- Registers listeners via subscribe(listener)
- Handles unregistering of listeners via the function returned by subscribe(listener)

```
import { createStore } from 'redux'
import todoApp from './reducers'
const store = createStore(todoApp)
```

There is only a signle store in a Redux application.

<br />

## React-redux
Official React bindings for Redux

- https://react-redux.js.org/

<br />

## Reference

- Redux official website: https://redux.js.org/

- Why use Redux? Reasons with clear examples: https://blog.logrocket.com/why-use-redux-reasons-with-clear-examples-d21bffd5835/

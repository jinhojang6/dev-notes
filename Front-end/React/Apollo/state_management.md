## Apollo Client State management
Apollo Client (>= 2.5) has built-in local state handling capabilities that allow you to store your local data inside the Apollo cache alongside your remote data.

We recommend managing local state in the Apollo cache instead of bringing in another state management library like Redux so the Apollo cache can be a single source of truth.

Managing local data with Apollo Client is very similar to how you've already managed remote data in this tutorial. You'll write a client schema and resolvers for your local data. You'll also learn to query it with GraphQL just by specifying the @client directive.

```
import { ApolloProvider, useQuery } from '@apollo/react-hooks'; 
import gql from 'graphql-tag';

import Pages from './pages';
import Login from './pages/login';
import injectStyles from './styles';

const IS_LOGGED_IN = gql`
  query IsUserLoggedIn {
    isLoggedIn @client
  }
`;

function IsLoggedIn() {
  const { data } = useQuery(IS_LOGGED_IN);
  return data.isLoggedIn ? <Pages /> : <Login />;
}

injectStyles();
ReactDOM.render(
  <ApolloProvider client={client}>
    <IsLoggedIn />
  </ApolloProvider>,
  document.getElementById('root'),
);
```

- Reference: [Manage local state](https://www.apollographql.com/docs/tutorial/local-state/#gatsby-focus-wrapper)

<br />

## Local state management

1. Direct Writes

- Directly write to the cache by calling cache.writeData

- Ideally, we use this approach for mutations that don’t depend on the data that’s currently in the cache

2. useMutation Hook

- `useMutation` hook with a GraphQL mutation that calls a local client-side resolver.

- At first, we need to write a Graphql mutation and it will be passed to useMutation.
```
const UPDATE_COUNTER = gql`
  mutation updateCounter($offset: Number!) {
    updateCounter(offset: $offset) @client
  }
`;
```

- Ideally, we use this approach for mutations that depend on the data that’s currently in the cache

- Reference: [Apollo local state management in React using GraphQL](https://medium.com/everestengineering/apollo-local-state-management-in-react-a481d95c1ce)

<br />
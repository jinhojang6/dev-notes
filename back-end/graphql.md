
## GraphQL
GraphQL is a query language for APIs and a runtime for fulfilling those queries with your existing data.
```
# References
Official homepage: https://graphql.org/
How to GraphQL: https://www.howtographql.com/
GraphQL + Apollo + React: https://flaviocopes.com/apollo/
```

<br/>

## Schema
Schema specifies the capabilities of the API and defines how clients can request the data.
```
type Query {
  allPersons(last: Int): [Person!]!
}

type Mutation {
  createPerson(name: String!, age: Int!): Person!
}

type Subscription {
  newPerson: Person!
}

type Person {
  name: String!
  age: Int!
  posts: [Post!]!
}

type Post {
  title: String!
  author: Person!
}

https://www.howtographql.com/basics/2-core-concepts/
```

<br/>

## Query
GraphQL APIs typically only expose a single endpoint. This works because the structure of the data that’s returned is not fixed. Instead, it’s completely flexible and lets the client decide what data is actually needed.
```
# Request
{
  allPersons {
    name
  }
}

# Response
{
  "data": {
    "allPersons": [
      {
        "name": "Johnny"
      },
      {
        "name": "Sarah"
      },
      {
        "name": "Alice"
      }
    ]
  }
}

https://www.howtographql.com/basics/2-core-concepts/
```

<br/>

## Mutation
There generally are three kinds of mutations:
- creating new data
- updating existing data
- deleting existing data

```
# Request
mutation {
  createPerson(name: "Bob", age: 36) {
    name
    age
  }
}

# Response
{
  "data": {
    "createPerson": {
      "name": "Bob",
      "age": 36
    }
  }
}

https://www.howtographql.com/basics/2-core-concepts/
```

<br/>

## Subscription
Realtime Updates.  Unlike queries and mutations that follow a typical “request-response-cycle”, subscriptions represent a stream of data sent over to the client.

```
# Request
subscription {
  newPerson {
    name
    age
  }
}

# Response
{
  "newPerson": {
    "name": "Jane",
    "age": 23
  }
}


https://www.howtographql.com/basics/2-core-concepts/
```

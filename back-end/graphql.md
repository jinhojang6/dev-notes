
## GraphQL
GraphQL is a query language for APIs and a runtime for fulfilling those queries with your existing data.
```
# References
Official homepage - https://graphql.org/
How to GraphQL - https://www.howtographql.com/
GraphQL + Apollo + React - https://flaviocopes.com/apollo/
Strapi + GraphQL - https://strapi.io/blog/build-a-blog-with-next-react-js-strapi-and-apollo
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

## Resolver
In the GraphQL server implementation, each of these fields actually corresponds to exactly one function that’s called a resolver. The sole purpose of a resolver function is to fetch the data for its field.

When the server receives a query, it will call all the functions for the fields that are specified in the query’s payload. It thus resolves the query and is able to retrieve the correct data for each field. Once all resolvers returned, the server will package data up in the format that was described by the query and send it back to the client.

A resolver function receives four arguments:

- `obj` The previous object, which for a field on the root Query type is often not used.
- `args` The arguments provided to the field in the GraphQL query.
- `context` A value which is provided to every resolver and holds important contextual information like the currently logged in user, or access to a database.
- `info` A value which holds field-specific information relevant to the current query as well as the schema details, also refer to type GraphQLResolveInfo for more details.

```
Query: {
  human(obj, args, context, info) {
    return context.db.loadHumanByID(args.id).then(
      userData => new Human(userData)
    )
  }
}

https://graphql.org/learn/execution/#root-fields-resolvers
https://www.howtographql.com/basics/3-big-picture/
```

<br/>

## Filter
similar to a where clause

```
const QUERY = gql`
query Tasks {
    tasks(where: { id: [${router.query.id}] }) {
    id
    name
    url
    description
    status
    videos {
        url
    }
    }
}
`;
```

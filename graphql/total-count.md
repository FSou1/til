# How to implement total count with GraphQL

A good practice for adding the total count property is to introduce a 'connection' type and wrap the items with it. In this case, the `totalCount` property and `items` are placed on the same level.

```gql
type Query {
  allLocations: LocationsConnection
}

type LocationsConnection {
  totalCount: Int
  locations: [Location]
}
```

Next, you should implement a totalCount resolver:

```typescript
export const resolvers = {
  Query:
  {
    allLocations: () => ({
      totalCount: allLocationsTotalCount(),
      locations: allLocations()
    })
  }
}
```

The rest of the methods are just the implementation details that could be omitted here.

Another approach is to name the wrapper as a plural form of the entity it enumerates, like:

```gql
type Episodes {
  info: Info
  results: [Episode]
}

type Episode {
  id: ID
  name: String
  air_date: String
}

type Info {
  count: Int
  pages: Int
  next: Int
  prev: Int
}
```

References:
* https://graphql.org/learn/pagination/
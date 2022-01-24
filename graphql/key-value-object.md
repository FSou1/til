# Is there a way to represent an object of key-value pairs in GraphQL

The GraphQL specification includes default scalar types `Int`, `Float`, `String`, `Boolean`, and `ID`. If you need to support other data types (e.g. `Date`), you can define custom scalar types.

Define a scalar type:

```graphql
# types.graphql

scalar JSONObject
```

Implement a type (or use one from the package, like [graphql-type-json](https://github.com/taion/graphql-type-json/blob/master/src/index.js)):

```typescript
# graphql-type-json.ts

export const GraphQLJSONObject = new GraphQLScalarType({
  name: 'JSONObject',
  description: 'The `JSONObject` scalar type...',
  serialize(value) {
    ...
  },
  parseValue(value) {
    ...
  },
  parseLiteral(ast) {
    ...
  },
});
```

Make the type a part of the resolvers:

```typescript
# resolvers.ts

import { GraphQLJSONObject } from './graphql-type-json.ts';

export const resolvers = {
  JSONObject: GraphQLJSONObject
}
```

References:
* https://www.apollographql.com/docs/apollo-server/schema/custom-scalars/
* https://stackoverflow.com/questions/39697575/is-there-a-way-to-represent-an-object-of-key-value-pairs-in-graphql
* https://github.com/taion/graphql-type-json/blob/master/src/index.js
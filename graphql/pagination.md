# How to implement pagination with GraphQL

There are various ways of implementing pagination. My favorite is using `offset` and `limit`. If prefer it over `cursor` or `page` / `display_on_page` because of it's simplicity. You don't need to calculate anything, just pass raw values.

First, add these properties as variables to a GraphQL query:

```graphql
type Query {
  allPositions(limit: Int, offset: Int): [Position!]!
}
```

Second, add them to the `allPositions` resolver:

```typescript
export const resolvers = {
  Query:
  {
    allPositions: (_: any, { limit, offset }: { limit: number, offset: number }) => allPositions(limit, offset),
  }
}
```

Finally, use them in a data fetching query. I'm using MongoDB with Deno, so this is how it looks:

```typescript
export const allPositions = async (limit: number, offset: number) => {
  const db = database();

  const positions = db.collection<PositionSchema>("positions");

  return await positions.find({}, FIND_OPTIONS).skip(offset).limit(limit).toArray();
}
```

If you were to use SQL, then it would be:

```sql
SELECT * FROM dbo.Positions OFFSET @offset FETCH @limit
```

where `@offset` and `@limit` are the variables.
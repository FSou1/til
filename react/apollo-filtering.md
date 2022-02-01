# How to implement filtering with GraphQL

This approach is used with React, GraphQL, Apollo, and the `useQuery` hook.

First, the GraphQL query should support filtering with variables, for example:

```graphql
  query ALL_POSITIONS($remote_work_allowed: Boolean) {
    allPositions(remote_work_allowed: $remote_work_allowed) {
      _id
      position_id
    }
  }
```

Next, you need to deconstruct the `refetch` function from the `useQuery` hook:

```typescript
const { data, error, loading, refetch } = useQuery(ALL_POSITIONS_QUERY);
```

Finally, you invoke that `refetch` function with the query variable:

```typescript
const onFiltersChange = ({ remote_work_allowed }: any) => {
  refetch({
    remote_work_allowed,
  });
};
```

The complete code:

```typescript
export const ALL_POSITIONS_QUERY = gql`
  query ALL_POSITIONS($remote_work_allowed: Boolean) {
    allPositions(remote_work_allowed: $remote_work_allowed) {
      _id
      position_id
    }
  }
`;

export default function PositionsWithData() {
  const onFiltersChange = ({ remote_work_allowed }: any) => {
    refetch({
      remote_work_allowed,
    });
  };

  const { data, error, loading, refetch } = useQuery(ALL_POSITIONS_QUERY);

  if (loading) return <p>Loading...</p>;
  if (error) return <p>Something went wrong: {error.message}</p>;

  return (
    <>
      <PositionFilters onChange={onFiltersChange} />

      <Positions entries={data.allPositions || []} />
    </>
  );
}
```

> You call `refetch` with a new set of variables, there is no need to specify original values. [Read more](https://www.apollographql.com/docs/react/data/queries/#providing-new-variables-to-refetch)

References:
* https://www.apollographql.com/blog/apollo-client/how-to-filter-and-search-using-variables-in-apollo-client/
* https://www.apollographql.com/docs/react/data/queries/#providing-new-variables-to-refetch
# How to use useQuery during server-side rendering?

Insead of using `useQuery`, you should initialize an `ApolloClient` and call the `query` method:

Init a client:

```typescript
# lib/apollo.ts

const apolloClient = new ApolloClient({
  uri: "http://localhost:3001/graphql",
  cache: new InMemoryCache(),
});
```

getStaticPaths:

```typescript
# position/[id].tsx

export async function getStaticPaths() {
  const { data } = await apolloClient.query({ query: ALL_POSITIONS_QUERY });

  const paths = data.allPositions.map((item: any) => ({
    params: { id: item._id },
  }));

  return {
    paths,
    fallback: false,
  };
}
```

getStaticProps:

```typescript
# position/[id].tsx

export async function getStaticProps({ params }: any) {
  const { id } = params;

  const { data } = await apolloClient.query({
    query: POSITION_QUERY,
    variables: { id },
  });

  return {
    props: {
      position: data.position,
    },
  };
}
```

References:
* https://stackoverflow.com/questions/67163527/does-usequery-run-on-server-side-rendering
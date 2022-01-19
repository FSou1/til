# How to set up Apollo Client and execute GraphQL queries

In order to execute GraphQL queries in Next.js, you need to:

1. Install the `npm i @apollo/client`

2. Define the `apolloClient`:

```typescript
# lib/apollo.ts

import { ApolloClient, InMemoryCache } from "@apollo/client";

const apolloClient = new ApolloClient({
  uri: "http://localhost:3000/api/graphql",
  cache: new InMemoryCache()
})

export default apolloClient;
```

3. Add the `ApolloProvider` as a wrapper and use the `apolloClient`:

```typescript
# pages/_app.tsx

import { ApolloProvider } from "@apollo/client";
import apolloClient from "../lib/apollo";

function MyApp({ Component, pageProps }: AppProps) {
  return (
    <ApolloProvider client={apolloClient}>
      <Component {...pageProps} />
    </ApolloProvider>
  );
}

export default MyApp;
```

After that you can execute a GraphQL query in a component, e.g.:

```typescript
import { useQuery } from "@apollo/client";
import gql from "graphql-tag";

export const ALL_POSITIONS_QUERY = gql`
  query {
    allPositions {
      _id
      role_name
    }
  }
`;

export default function Positions() {
  const { data, error, loading } = useQuery(ALL_POSITIONS_QUERY);

  if(loading) return <p>Loading...</p>

  if(error) return <p>Something went wrong: {error.message}</p>

  return (
    <div>
      <h1>Positions</h1>
      
      {data.allPositions.map((position) => (
        <Position key={position._id} position={position} />
      ))}
    </div>
  );
}
```

References:
* https://www.youtube.com/watch?v=K8gOiyHX91M
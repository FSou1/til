# How to call an external GraphQL server

If you app runs on `:3000` and you try to make an HTTP request to a GraphQL server, that runs on `:3001`, you'll get a CORS error:

```
Cross-Origin Request Blocked: The Same Origin Policy disallows reading the remote resource at http://localhost:3001/graphql. (Reason: CORS header ‘Access-Control-Allow-Origin’ missing). Status code: 405.

Cross-Origin Request Blocked: The Same Origin Policy disallows reading the remote resource at http://localhost:3001/graphql. (Reason: CORS request did not succeed). Status code: (null).
```

In order to fix this, you'll need to stop calling external web server from client and call the `:3000` instead. The problem is that you still need to proxy your GraphQL requests from `:3000` to `:3001`.

In Next.js you can use `rewrites` for it. Update the `next.config.js` file like this:

```typescript
const nextConfig = {
  reactStrictMode: true,
  async rewrites() {
    return [
      {
        source: '/api/graphql',
        destination: 'http://localhost:3001/graphql'
      }
    ]
  }
}
```

Rebuild the app to apply the configuration changes.

Now, when you call a GraphQL server with the `ApolloClient` like this:

```typescript
const apolloClient = new ApolloClient({
  uri: "http://localhost:3000/api/graphql",
  cache: new InMemoryCache()
})
```

your requests will be redirected to the `http://localhost:3001/graphql`.

The reason why I'm doing so is because my GraphQL server is running with Deno (`:3001`) and the UI app with Next.js (`:3000`).

Another solution is to make your GraphQL server a part of your Next.js app.

References:
* https://stackoverflow.com/questions/65058598/nextjs-cors-issue
* https://nextjs.org/docs/api-reference/next.config.js/rewrites
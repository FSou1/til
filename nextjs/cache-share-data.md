# How to cache and share data at build time?

If you need to generate a page, you have to get all the data in `getStaticProps` and pass it to the page component. The problem is that page generation is done by workers in parallel, so each worker will request its own copy of data. If the data is fetched from a remote resource (such as an API), each worker will send its own request, that will degrade performance and waste resources.

You don't want your workers to retrieve hundreds and thousands of copies of your dictionaries or static data.

In order to fix this, you can:
- Run a local HTTP server that will respond with cached the results;
- For each page, fetch the data from this server in the `getStaticProps` function.

Let's say you need an array of locations to generate a page:

```typescript
# pages/position/[id].tsx

export async function getStaticProps({ params }: any) {
  const position = await getPosition(params.id);

  const locations = await fetchLocationsData();

  return {
    props: {
      position,
      locations
    },
  };
}
```

This is how you can access your local HTTP server:

```typescript
# lib/locations.ts

async function http<T>(request: RequestInfo): Promise<T> {
  const response = await fetch(request);
  const body = await response.json();
  return body;
}

export async function fetchLocationsData() {
  const URL = 'http://localhost:4000/locations';

  const { allLocations } = await http<{ allLocations: [] }>(URL);

  return allLocations;
}
```

Finally, here is the implementation of the web server, which only responsibility is to respond with the cached data:

```javascript
# lib/cache/locations.js

/* The function fetches data based on the URL */
async function handle(url) {
  switch (url) {
    case '/locations': {
      return await getLocations(GRAPHQL_ENDPOINT);
    }
    default: {
      console.log(`Unsupported: url '${url}' is not supported`);
      return;
    }
  }
}

const map = new Map();

/* An HTTP request handler which:
- fetches data if it's not cached yet
- or responds with the cached data */
async function handler(req, res) {
  if (map.has(req.url)) {
    const data = await map.get(req.url);

    res.writeHead(200, { "Content-Type": "application/json; charset=utf-8" });
    res.write(JSON.stringify(data));
    res.end();
    console.log(`📦 Cached request to: ${req.url}`);

    return;
  }

  const data = await handle(req.url);
  if (!data) {
    return;
  }

  map.set(req.url, data);

  res.writeHead(200, { "Content-Type": "application/json; charset=utf-8" });
  res.write(JSON.stringify(data));
  res.end();
  console.log(`📥 GET ${req.url}`);
}

/* Run the local server */
return http.createServer(handler).listen(PORT, HOST, async () => {
  console.log(`Server is running on 🌎 http://${HOST}:${PORT}`);
});
```

Finally, all you need to do is:
- Run the HTTP server with `node lib/cache/locations.js`
- Build the pages with `next build`

There are other solutions for this problem. For example, you can cache the data in a local file and access it by `fs`.

I don't like any of these solutions. They all require a lot of efforts to make it works. I don't know why data sharing is not a part of Next.js yet (for example, we could fetch the data once in `_app.tsx` and access it in the children pages).

In 2022, we're still waiting for [this feature](https://github.com/vercel/next.js/discussions/10949#discussioncomment-44898) to be implemented.

References:
* https://itnext.io/fetch-shared-data-in-next-js-with-single-request-833433fa8ed1
* https://flaviocopes.com/nextjs-cache-data-globally/
* https://github.com/akellbl4/cache-proxy
* https://github.com/vercel/next.js/discussions/10949#discussioncomment-44898
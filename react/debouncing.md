# How to debounce and throttle in React

The project I'm working on has a block of filters. One of the filter is a text input for full text search. Everytime a user changes the input value, the component notifies the parent component, that refetches the data (read [filtering with GraphQL](/react/apollo-filtering.md) for more details).

When the handler is invoked too often, we risk making the application lagging or even unresponsive for a few seconds. Debouncing and throttling techniques can help to address these issues.

There are diffrent ways how it can be implemented. You can find out various approached by the reference links.

This is how I did it with the `useMemo()` hook:

```typescript
import debounce from "lodash.debounce";

const handleTermChange = (e: ChangeEvent<HTMLInputElement>) => {
  const { value } = e.target;

  onChange({
    term: value,
  });
};

const debouncedHandleTermChange = useMemo(
  () => debounce(handleTermChange, 300), []
);
```

References:
* https://dmitripavlutin.com/react-throttle-debounce/
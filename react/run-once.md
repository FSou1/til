# How to run the code once

React has a built-in hook called `useEffect()`. This hook runs when the component renders. To ensure the `useEffect()` only runs once, you can pass the second argument as `[]`:

```javascript
import React, { useEffect } from 'react';

function App() {
  useEffect(() => {
    // Run! Like go get some data from an API.
  }, []);

  return (
    <div>
      {/* Do something with data. */}
    </div>
  );
}
```

> The second param is an array of variables that the component will check to make sure changed before re-rendering. 

References:
* https://css-tricks.com/run-useeffect-only-once/
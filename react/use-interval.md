# How to use setInterval

If you use `setInterval` as you usually do within a React component, the state won't be persisted. In order to fix this, you should use a [custom hook](https://github.com/donavon/use-interval/blob/master/src/index.tsx) that Dan Abramov wrote:

```javascript
import React, { useState, useEffect, useRef } from 'react';

function Counter() {
  let [count, setCount] = useState(0);

  useInterval(() => {
    // Your custom logic here
    setCount(count + 1);
  }, 1000);

  return <h1>{count}</h1>;
}
```

References:
* https://overreacted.io/making-setinterval-declarative-with-react-hooks/
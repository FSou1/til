# How to use jQuery

If you import jQuery into a react component and get a type definition error, you may need to install the jquery types:

```cmd
npm install --save-dev @types/jquery
```

This package solves the error like `$ is not defined` and allows you to use jQuery within a React app.

You may want to import jQuery explicitly:

```typescript
import $ from 'jquery'
```

According to react docs:

> Just because it’s possible, doesn’t mean that it’s the best approach for React apps. We encourage you to use React components when you can.

References:
* 
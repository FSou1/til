# How to handle checkbox change in React

In order to react on a checkbox value change, you should:

1. Define a function to handle updates:

```typescript
const handleChange = (e: ChangeEvent<HTMLInputElement>) => {
  const { checked } = e.target;

};
```

2. Use this function in the `onChange` attribute:

```html
<input
  type="checkbox"
  id="remote_work_allowed"
  name="remote_work_allowed"
  onChange={(e) => handleChange(e)}
/>
```
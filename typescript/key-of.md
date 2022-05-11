# How to limit values to keys of an object

Use the `keyof` operator:

```typescript
type Point = { x: number; y: number };

function print(key: keyof Point) {
  // key value can only be 'x' or 'y'
}
```

References:
* https://www.typescriptlang.org/docs/handbook/2/keyof-types.html
# How to specify inline styles with the `styles` property

You can use the `style` property, but the value should be an object:

```typescript
function ToDoApp() {
  return (
    <div style={ { backgroundColor: "#44014C", width: "300px", minHeight: "200px"} }>
      ...
    </div>
  );
}
```

The first curly bracket specifies an expression, the second one starts the object declaration.

Since the style property expects an object, the value can be assigned to a variable and initiated by some logic.

```typescript
function ToDoApp() {
  const styleObject = {
    backgroundColor: "#44014C",
    width: "300px",
    minHeight: "200px"
  };

  return (
    <div style={ styleObject }>
      ...
    </div>
  );
}
```

References:
* https://blog.logrocket.com/the-best-styling-in-react-tutorial-youve-ever-seen-676f1284b945/
# How to apply class names conditionally

In order to apply class names dynamically, you can build a string on the fly and set the `className` property:

```javascript
<div className={"btn-group pull-right " + (this.props.showBulkActions ? 'show' : 'hidden')}>
```

References:
* https://stackoverflow.com/a/30533260/2524304
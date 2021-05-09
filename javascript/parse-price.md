# How to parse a price string

In order to parse the `$1,598.99` price, you can use the following snippet:

```javascript
function parsePrice(str) {
    return parseFloat(str.replace(/[$,]/g, ""));
}
```

References:
* https://stackoverflow.com/a/26321468/2524304
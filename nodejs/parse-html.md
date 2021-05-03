# How to parse an HTML page with Node.js

You can use the [jsdom](https://www.npmjs.com/package/jsdom) npm package:

```javascript
const jsdom = require("jsdom");
const { JSDOM } = jsdom;
const querySelector = "#outOfStock";
const dom = new JSDOM(html);
dom.window.document.querySelector(querySelector) // an HTML node or null
```

References:
* https://www.npmjs.com/package/jsdom
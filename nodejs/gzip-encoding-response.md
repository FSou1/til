# How to decode a GZip response with Node.js

The easiest way to decode a GZip response with Node.js is to use a deprecated `request` npm module:

```javascript
var request = require('request');

const options = {
    method: 'GET',
    uri: 'https://google.com',
    gzip: true
};

request(options, function (error, response, body) {
    // body is the decompressed response body
    console.log('response body: ' + body);
});
```

References:
* https://stackoverflow.com/a/28583320/2524304
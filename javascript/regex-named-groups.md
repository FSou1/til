# Use named groups with regular expressions

In order to use named groups, we can add angled brackets in a regular expression like this:

```javascript
const message = "Error 400: Your client has issued an illegal request";

const regex = /Error (?<code>\w+): (?<message>.*$)/;

const match = regex.exec(message);

console.log(match.groups.code);    // 400

console.log(match.groups.message); // Your client has issued an illegal request
```

References:
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Groups_and_Ranges
# How to parse an HTML page with React

You can use the [node-html-parser](https://www.npmjs.com/package/node-html-parser) npm package:

```javascript
import { parse } from 'node-html-parser';

function App() { 
  const root = parse('<ul id="list"><li>Hello World</li></ul>');

  const text = root.querySelector('#list li').innerText;
  
  return (
    <div>
      {text}
    </div>
  );
}

export default App;
```

References:
* https://www.npmjs.com/package/node-html-parser
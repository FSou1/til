# How to add meta tags

There are various ways how you can add and control meta tags. One of them is to use the https://www.npmjs.com/package/react-helmet package.

Install:

```
npm i react-helmet
```

Use:

```typescript
import './App.css';
import { Helmet } from 'react-helmet';

function App() {
  return (
    <div>
      <Helmet>
        <title>Portfolio::Marvel Template</title>
        <meta charSet="utf-8" />
        <meta name="description" content="Description text" />
        <meta name="author" content="Author text" />
      </Helmet>
    </div>
  );
}

export default App;
```

References:
* https://www.youtube.com/watch?v=DQahXIcvRpM
# How to create a layout

In order to reuse common elements (e.g. toolbar, sidebar) and render page content (e.g. `<p>Test</p>`), we can use the `props.children` property:

Layout.js:
```javascript
const layout = (props) => (
    <div>
        <div>Toolbar, sidebar, backdrop</div>
        <main>
            {props.children}
        </main>
    </div>
);

export default layout;
```

App.js:
```javascript
import Layout from './components/Layout/Layout';

function App() {
  return (
    <Layout>
      <p>Test</p>
    </Layout>
  );
}

export default App;
```

References:
* https://dev.to/olenadrugalya/layout-component-and-why-we-use-it-in-react-d8b
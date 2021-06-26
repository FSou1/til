# How to render components without a root wraper

There can only be a single root element in a react component.

Instead of always using the root `<div>...</div>` element, we can either use the [react-aux](https://www.npmjs.com/package/react-aux) package or implement the `Aux` component on our own:

Aux.js (*Aux is reserved on Win*):
```javascript
const aux = (props) => props.children;

export default aux;
```

Layout.js:
```javascript
import Aux from '../../hoc/Auxx';

const layout = (props) => (
    <Aux>
        <div>Toolbar, sidebar, backdrop</div>
        <main>
            {props.children}
        </main>
    </Aux>
);

export default layout;
```

The output HTML markup:
```html
<div id="root">
    <div>Toolbar, sidebar, backdrop</div>
    <main>
        <p>Test</p>
    </main>
</div>
```

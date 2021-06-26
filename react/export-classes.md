# How to import CSS classes and use them in a component

Let's say we have a `layout.css` file:

```css
.Content {
    margin-top: 16px;
}
```

In order to use the `Content` rule, we can import `classes` right into the component:

```javascript
import classes from './Layout.css';

const layout = (props) => (
    <div className={classes.Content}>
        {props.children}
    </div>
);

export default layout;
```

Since the CSS file has been processed (optimized), the output class name was `_2jRP1cgez_J6jwdMTdOBui`.

Output HTML markup:

```html
<div class="_2jRP1cgez_J6jwdMTdOBui">
    <p>Test</p>
</div>
```

If you are wondering what `classes` actually is, then let me answer that it is just a plain object:

```javascript
{
    Content: "_2jRP1cgez_J6jwdMTdOBui"
}
```

By default, neither the react nor the app does not throw any errors if the CSS rule does not exist.

References:
* https://www.robinwieruch.de/react-css-styling
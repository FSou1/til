# How to pass CSS styles to a child component

If you have a component whose styles are controlled by multiple parent components, then you can pass the style as a `prop` and render it with `{{}}`:

Logo.js:

```javascript
const logo = (props) => (
    <div className={classes.Logo} style={{height: props.height}}>
        <img src={burgerLogo} alt="MyBurger" />
    </div>
);

export default logo;
```

Toolbar.js:

```javascript
const toolbar = () => (
    <header>
        <Logo height="80%" />
    </header>
);

export default toolbar;
```
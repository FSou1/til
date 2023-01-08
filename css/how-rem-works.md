# How rem units work

In CSS rem stands for “root em”, a unit of measurement that represents the font size of the root element.

This means that 1rem equals the font size of the html element, which for most browsers has a default value of 16px.

In the example above, since 1rem = 16px, `font-size` will be 32px and `max-width` will become 800px.

```css
html {
  font-size: 16px;
}

.test {
  max-width: 50rem;
  font-size: 2rem;
  color: white;
}
```

However, if you change the html `font-size` to `10px`, then the `.test` content will shrink to `font-size` = 20px and `max-width` = 500px.

## Rem vs Em

Rem units are related to the root element, while em are calculated based on the element itself.

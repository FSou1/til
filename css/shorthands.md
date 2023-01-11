# CSS Shorthands

## currentColor

The currentcolor property allows you to use the current value of the color property, without writing the actual color value.

```css
.link:link,
.link:visited {
  color: #e67e22;
  border-bottom: 1px solid currentColor;
}
```

```css
body {
  color: red;
}

div {
  border: 5px solid currentcolor;
}
```

## transparent

The transparent keyword can be used anywhere a color value is accepted. This allows you to set items to transparent, so that any background element will show through.

```css
.link:hover,
.link:active {
  border-bottom: 1px solid transparent;
}
```

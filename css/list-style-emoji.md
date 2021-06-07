# Styling list bullets with emoji

There are at multiple ways how it can be done.

One of them is to use the `::before` pseudo-element:

```css
ul {
    list-style: none;
    padding-left: 0;
    margin-left: 0;
}

li::before {
    content: "✔ ";
}

li:nth-child(3n+4)::before {
    content: "🐶 ";
}
```

The HTML markup is basic:
```html
<ul>
    <li>Arrange your photoshoots</li>
    <li>Automate appointments</li>
    <li>Reduce manual admin work</li>
    <li>Focus on your business</li>
</ul>
```

References:
* https://www.clairecodes.com/blog/2019-04-26-styling-list-bullets-with-emoji/
* https://codepen.io/clairecodes/pen/moNmXp
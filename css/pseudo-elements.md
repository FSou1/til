# What pseudo-elements are availabine in CSS?

## ::first-line

The ::first-line pseudo-element is used to add a special style to the first line of a text.

## ::first-letter

The ::first-letter pseudo-element is used to add a special style to the first letter of a text.

## ::before

The ::before pseudo-element can be used to insert some content before the content of an element.

```css
h1::before {
  content: url(smiley.gif);
}
```

## ::after

The ::after pseudo-element can be used to insert some content after the content of an element.

```css
h1::after {
  content: url(smiley.gif);
}
```

## ::marker

The ::marker pseudo-element selects the markers of list items.

```css
::marker {
  color: red;
  font-size: 23px;
}
```

## ::selection

The ::selection pseudo-element matches the portion of an element that is selected by a user.

```css
::selection {
  color: red;
  background: yellow;
}
```

# How to add a class name to a DOM element with JavaScript

If there is a link to a DOM element, then we can use the `add` method of the `classList` property:

```javascript
const element = document.querySelector('.after');

element.classList
    .add('fade-in-animation');
```

References:
* https://developer.mozilla.org/en-US/docs/Web/API/Element/classList
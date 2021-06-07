# How to toggle a class of a DOM element with JavaScript

If there is a link to a DOM element, then we can use the `toggle` method of the `classList` property:

```javascript
const element = document.querySelector('.after');

element.classList
    .toggle('hidden');
```

References:
* https://developer.mozilla.org/en-US/docs/Web/API/Element/classList
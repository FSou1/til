# How to fix Property 'X' does not exist on type

Let's say you have the following code:

```typescript
$('.owl-carousel').owlCarousel({
    items: 1,
    loop:true,
    margin:10,
    nav:true
});
```

If the `owlCarousel` method is not defined, you'll get an error message: `Property 'owlCarousel' does not exist on type 'JQuery<HTMLElement>'`.

In order to fix it, you can use a variable of type `any`:

```typescript
const carousel = $('.owl-carousel') as any;

$('.owl-carousel').owlCarousel({
    items: 1,
    loop:true,
    margin:10,
    nav:true
});
```

References:
* https://stackoverflow.com/questions/18083389/ignore-typescript-errors-property-does-not-exist-on-value-of-type
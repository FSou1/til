# How to run a jQuery code after render

Let's say you have a 3rd party plugin. Once the component is rendered, you need to run a plugin initialization code:

```typescript
carousel.owlCarousel({
    items: 1,
    loop:true,
    margin:10,
    nav:true
});
```

In this case, as we do with any other custom code, we can use the `useEffect` hook:

```typescript
import { useEffect } from 'react';

const Projects = () => {
    useEffect(() => {
        const carousel = $('.owl-carousel') as any;

        carousel.owlCarousel({
            items: 1,
            loop:true,
            margin:10,
            nav:true
        });
    });

    return (
        ...
    );
}
```

> If you're experiencing an error like `Property 'owlCarousel' does not exist on type 'JQuery<HTMLElement>'.`, you can fix it with a variable of type `any`.

References:
* https://stackoverflow.com/questions/26556436/react-after-render-code
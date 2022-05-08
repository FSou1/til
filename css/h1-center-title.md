# How to put a title (h1) in the center of the div

![alt text](./h1-center.png)

HTML:

```html
<header class="header">
    <div class="text-box">
        <h1 class="heading-primary">
            <span class="heading-primary-main">Outdoors</span>
            <span class="heading-primary-sub">is where life happens</span>
        </h1>
    </div>
</header>
```

CSS:

The trick here is: first, align the `text-box` div to `top: 40%` and `left: 50%`:

![alt text](./h1-center-50.png)

And then, transform the it's position by cutting the offset by `-50%` both horizonally and vertically.

```css
.text-box {
  /* Align in the scope of the image */
  position: absolute;

  /* The top left point of the div
    is shifted by 40 and 50 */
  top: 40%;
  left: 50%;

  /* Move the top left coordinate back by -50% */
  transform: translate(-50%, -50%);
}

.heading-primary {
  color: #fff;
  text-transform: uppercase;
}

.heading-primary-main {
  display: block;
  font-size: 60px;
  font-weight: 400;
  letter-spacing: 35px;
}

.heading-primary-sub {
  display: block;
  font-size: 20px;
  font-weight: 700;
  letter-spacing: 17.4px;
}
```


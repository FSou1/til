# How to align a logo with absolute positioning

How would you make this logo aligned to the top left corner of the image?

![alt text](./logo-position.png)

HTML:

```html
<header class="header">
  <div class="logo-box">
      <img src="img/logo-white.png" class="logo" />
  </div>
</header>
```

CSS:

```css
.header {
  position: relative;
}

.logo-box {
  position: absolute;
  top: 40px;
  left: 40px;
}

.logo {
  height: 35px;
}
```

From now on, the base point of the logo is the top left corner of the image.


References:
* https://www.udemy.com/course/advanced-css-and-sass/

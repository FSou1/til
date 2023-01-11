# How to add a nice scaling effect on image hover?

```html
<div class="gallery">
  <figure class="gallery-item">
    <img class="gallery-image" src="img/gallery/gallery-1.jpg" />
  </figure>
</div>
```

```css
.gallery-image:hover {
  transform: scale(1.1);
  transition: all 0.4s;
}

.gallery-item {
  overflow: hidden;
}
```

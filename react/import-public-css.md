# How to use a css file from the public folder

The same way we access any file from the `public` folder, you can either:

* use the `%PUBLIC_URL%`:

```html
<link rel="stylesheet" href="%PUBLIC_URL%/css/bootstrap.min.css">
```

* or expect it to be available by the root:

```html
<link rel="stylesheet" href="/css/bootstrap.min.css">
```

References:
* https://create-react-app.dev/docs/using-the-public-folder/
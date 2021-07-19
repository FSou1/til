# How to use an image from the public folder

In order to access an image, that is located in the public folder, you can either:

* use the `%PUBLIC_URL%`:

```html
<link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
```

* or expect it to be available by the root:

```html
<img src="/images/project/project-image01.png" />
```

References:
* https://stackoverflow.com/questions/47196800/reactjs-and-images-in-public-folder
* https://stackoverflow.com/questions/42296499/how-to-display-svg-icons-svg-files-in-ui-using-react-component
* https://create-react-app.dev/docs/using-the-public-folder/
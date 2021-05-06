# How to fix 'Refused to execute inline script' (Chrome extension)

If you are using [create-react-app](https://github.com/facebook/create-react-app) and experiencing the `Refused to execute inline script because it violates the following Content Security Policy directive` error, you should:

1. create a `.env` file in the project root
2. Add a `INLINE_RUNTIME_CHUNK=false` variable
3. Build the project and reload the extension

References:
* https://stackoverflow.com/a/59628844/2524304
# How to toggle password visibility

All you need to do is to change the `type` property of the element from `password` to `text` back and forth:

```html
<input
    type="password"
    class="input_password"
    oninput="onPasswordChange(this)">
```

```javascript
function togglePassword() {
    const password = document.querySelector('.input_password');

    if(password.type === 'password') {
        password.type = 'text';
    } else {
        password.type = 'password';
    }
}
```

References:
* https://www.w3schools.com/howto/howto_js_toggle_password.asp
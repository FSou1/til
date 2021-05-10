# How to display a notification (Chrome extension)

In order to display built-in browser notifications with chrome, you should:
* Add the `notifications` permission
* Use the `chrome.notifications.create` method

The following code displays a notification:

```javascript
const options = {
    iconUrl: chrome.runtime.getURL('logo192.png'),
    title: notificationOptions.title,
    message: notificationOptions.message,
    type: 'basic'
};
chrome.notifications.create(null, options);
```

> iconUrl, title, message, type are required for `notifications.create` method

References:
* https://stackoverflow.com/questions/18797636/how-to-create-a-notification-chrome-extension
* https://developer.chrome.com/docs/extensions/reference/notifications/#type-TemplateType
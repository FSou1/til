# How to use optional route parameters in Express

You can use the `?` character to make the parameter optional:

```
/articles/:year?/:month?/:day?
```

Or:

```javascript
router.delete('/:source?/:model?', itemDataController.remove);
```

References:
* https://stackoverflow.com/questions/41736413/multiple-optional-route-parameters-in-express

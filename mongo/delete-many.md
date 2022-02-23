# How to delete multiple documents in a single query

You can use the `deleteMany` method:

```javascript
db.getCollection('collection-name').deleteMany(
  {
    'externalId': {
      '$in': [
        '224844936430',
        '224844978951'
      ]
    }
  }
)
```

References:
* https://docs.mongodb.com/manual/reference/method/db.collection.deleteMany/#mongodb-method-db.collection.deleteMany
* https://stackoverflow.com/questions/18566590/remove-multiple-documents-from-mongo-in-a-single-query
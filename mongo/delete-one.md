# How to delete a document by id

You can use the `deleteOne` method:

```javascript
db.getCollection('price-data')
  .deleteOne(
    {
      '_id': ObjectId('625c9f9429ab7ab51461e092')
    }
  );
```
# How to return more than 20 items from MongoDB

By default, MongoDB prints up to the first 20 documents that match the query.

You can either set `DBQuery.shellBatchSize` to increase the limit or use the `toArray()` method:

```javascript
// The current database to use.
use('prices-database');

// Search for documents in the current collection.
db.getCollection('items')
  .find({ date: "2022-03-28" })
  .toArray()
  .map(item => item.price + item.shippingPrice);
```

This query has been successfully run with the [MongoDB for VS Code](https://marketplace.visualstudio.com/items?itemName=mongodb.mongodb-vscode) extension.

References:
* https://www.mongodb.com/docs/manual/tutorial/configure-mongo-shell/#change-the-mongo-shell-batch-size
* https://stackoverflow.com/questions/3705517/how-to-print-out-more-than-20-items-documents-in-mongodbs-shell
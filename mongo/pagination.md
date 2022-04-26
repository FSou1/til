# How to implement pagination

One of the way to implement pagination is to use `skip` and `limit` methods:

```javascript
const data = await db
  .collection<any>('items-data')
  .find({ model: model })
  .sort({ 'time': 1 })
  .skip(page > 0 ? ((page - 1) * PER_PAGE) : 0)
  .limit(PER_PAGE)
  .toArray();
```

1. Filter out documents with `find`
2. Sort by a prop with `sort`
3. Skip either 0 or `page * PER_PAGE`
4. Limit the result with `limit`

References:
* https://www.mongodb.com/docs/manual/reference/method/cursor.skip/
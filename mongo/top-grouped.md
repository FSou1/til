# How to select top N rows groupped by date

You need to first sort the documents by the fields (`$sort`), then do an initial group (`$group`), and after that slice the array (`$project > $slice`).

```javascript
db.getCollection('price-data')
  .aggregate([
    { '$sort': { 'model': 1, 'time': -1 } },
    {
      '$group': {
        '_id': '$model',
        'recent': { '$push': '$$ROOT'}
      }
    },
    {
      '$project': {
        'recent': {
          '$slice': ['$recent', 2]
        }
      }
    }
  ]);
```

Output:

```json
[
  {
    "_id": "3070",
    "recent": [
      {
        "_id": {
          "$oid": "625c0153b0117ceb7fae24c2"
        },
        "time": "2022-04-16",
        "model": "3070"
      },
      {
        "_id": {
          "$oid": "625c0153b0117ceb7fae24c3"
        },
        "time": "2022-04-15",
        "model": "3070"
      }
    ]
  }
]
```
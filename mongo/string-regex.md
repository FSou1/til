# How to check if a field contains a string

I want to fetch documents with model that contain "3060" and with titles that don't contain "3060".

You can use `$regex` operator:

```json
{
  "model": { $regex: "3060" },
  "title": { $not: { $regex: "3060" } }
}
```

References:
* https://stackoverflow.com/questions/10610131/checking-if-a-field-contains-a-string
* https://stackoverflow.com/questions/52217384/how-to-query-on-mongodb-for-field-not-contain-a-string
# Adding explicit mappings

## Add field mappings for `reviews` index
```
PUT /reviews
{
  "mappings": {
    "properties": {
      "rating": { "type": "float" },
      "content": { "type": "text" },
      "product_id": { "type": "integer" },
      "author": {
        "properties": {
          "first_name": { "type": "text" },
          "last_name": { "type": "text" },
          "email": { "type": "keyword" }
        }
      }
    }
  }
}
```

## Index a test document
```
PUT /reviews/_doc/1
{
  "rating": 5.0,
  "content": "content text goes here.",
  "product_id": 1,
  "author": {
    "first_name": "Nitin",
    "last_name": "Singh",
    "email": "nitin.kumar@tothenew.com"
  }
}
```
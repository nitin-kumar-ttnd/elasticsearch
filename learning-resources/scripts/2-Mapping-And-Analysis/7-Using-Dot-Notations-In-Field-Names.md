# Using dot notation in field names

## Using dot notation for the `author` object
In place of nested object dot notation can be used like below:
```
PUT /reviews2
{
  "mappings": {
    "properties": {
      "rating": { "type": "float" },
      "content": { "type": "text" },
      "product_id": { "type": "integer" },
      "author.first_name": { "type": "text" },
      "author.last_name": { "type": "text" },
      "author.email": { "type": "keyword" }
    }
  }
}
```

## Retrieve mapping
```
GET /reviews2/_mapping
```
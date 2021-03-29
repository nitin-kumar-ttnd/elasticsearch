# Searching for a term

## Matching documents with a value of `true` for the `is_active` field

```
GET /products/_search
{
  "query": {
    "term": {
      "is_active": true
    }
  }
}
```
Following one provides syntax to add more options in is_active
```
GET /products/_search
{
  "query": {
    "term": {
      "is_active": {
        "value": true
      }
    }
  }
}
```
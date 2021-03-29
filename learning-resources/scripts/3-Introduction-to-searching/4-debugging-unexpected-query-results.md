# Debugging unexpected query results

```
GET /products/_explain/1
{
  "query": {
    "term": {
      "name": "lobster"
    }
  }
}
```
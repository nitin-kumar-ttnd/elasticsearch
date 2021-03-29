# Understanding relevance scores
Adding explain will return _explanation in the results.
```
GET /products/_search
{
  "explain": true,
  "query": {
    "term": {
      "name": "lobster"
    }
  }
}
```
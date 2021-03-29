# Introducing the Query DSL

## Matching all documents
By default it resturns only 10 results.
```
GET /products/_search
{
  "query": {
    "match_all": {}
  }
}
```
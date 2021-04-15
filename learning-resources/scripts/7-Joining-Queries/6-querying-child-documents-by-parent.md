# Querying child documents by parent

## Matching child documents by parent criteria
Lets us define a query which parent doc should match and then return child doc.

```
GET /department/_search
{
  "query": {
    "has_parent": {
      "parent_type": "department",
      "query": {
        "term": {
          "name.keyword": "Development"
        }
      }
    }
  }
}
```

## Incorporating the parent documents' relevance scores
Now the relevance score of parent is taken into account and the results are returned according to that.
```
GET /department/_search
{
  "query": {
    "has_parent": {
      "parent_type": "department",
      "score": true,
      "query": {
        "term": {
          "name.keyword": "Development"
        }
      }
    }
  }
}
```
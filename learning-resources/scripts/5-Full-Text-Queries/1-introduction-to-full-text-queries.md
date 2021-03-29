# Introduction to full text queries

## Importing new test data
```
curl -H "Content-Type: application/x-ndjson" -XPOST "http://localhost:9200/recipe/_bulk?pretty" --data-binary "@recipes-bulk.json"
```

## Inspecting the mapping

```
GET /recipe/_mapping
```
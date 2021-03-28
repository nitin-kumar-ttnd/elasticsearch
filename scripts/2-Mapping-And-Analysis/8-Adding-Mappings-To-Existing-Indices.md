# Adding mappings to existing indices
ES doesnt not store when a document was indexed so we need to do it manually.
## Add new field mapping to existing index
```
PUT /reviews/_mapping
{
  "properties": {
    "created_at": {
      "type": "date"
    }
  }
}
```

## Retrieve the mapping
```
GET /reviews/_mapping
```
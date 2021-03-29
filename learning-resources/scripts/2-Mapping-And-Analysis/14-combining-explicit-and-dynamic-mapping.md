# Combining explicit and dynamic mapping
Dynamic mapping is enabled by default. You dont have to chose one over the other.
No mapping for `last_name` field here, so it would be mapped automatically.
## Create index with one field mapping
```
PUT /people
{
  "mappings": {
    "properties": {
      "first_name": {
        "type": "text"
      }
    }
  }
}
```

## Index a test document with an unmapped field
```
POST /people/_doc
{
  "first_name": "Bo",
  "last_name": "Andersen"
}
```

## Get mapping
```
GET /people/_mapping
```

## Delete the index
```
DELETE /people
```
# Mapping document relationships

```
PUT /department/_mapping
{
  "properties": {
    "join_field": { 
      "type": "join",
      "relations": {
        "department": "employee"
      }
    }
  }
}
```

Here we are defining parent-child relationship.
We can also define multiple children, in that case there would be array in case of single value.

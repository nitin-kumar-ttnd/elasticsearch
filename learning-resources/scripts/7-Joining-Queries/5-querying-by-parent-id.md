# Querying by parent
Which relation we are querying is specifid in type.
id should be of the parent. 
```
GET /department/_search
{
  "query": {
    "parent_id": {
      "type": "employee",
      "id": 1
    }
  }
}
```
#Updating Docs with Ids
**Just have to supply the body with fields which have to be updated**
```
POST /products/_update/100
{
  "doc": {
    "in_stock": 0
  }
}
```

**We can also add new fields**

```
POST /products/_update/100
{
  "doc": {
  "tags":["electronics"]  
  }
}
```

**Note:** No field is updated, the field   "result" : "noop" would be there in the response.


Important Points:
* Documents are immutable
* We actually replaced the documents using above commands.
* Saves network round trips.
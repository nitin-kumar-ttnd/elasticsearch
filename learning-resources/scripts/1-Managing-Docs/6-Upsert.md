#Upsert
Upserting means to conditionally update or insert a document based on whether or not
the document already exists.So if the document already exists, a script is run, and if it doesn't, a new document is indexed.

## Creating doc which doesnt exist
```
POST /products/_update/101
{
  "script": {
    "source": "ctx._source.in_stock++"
  },
  "upsert": {
    "name": "Blender",
    "price": 399,
    "in_stock": 5
  }
}
```

**Output**
```
{
  "_index" : "products",
  "_type" : "_doc",
  "_id" : "101",
  "_version" : 1,
  "result" : "created",
  "_shards" : {
    "total" : 3,
    "successful" : 1,
    "failed" : 0
  },
  "_seq_no" : 10,
  "_primary_term" : 2
}
```


## If we update already existing doc then status is update rather than created as in previous case
```
POST /products/_update/101
{
  "script": {
    "source": "ctx._source.in_stock++"
  },
  "upsert": {
    "name": "Blender",
    "price": 399,
    "in_stock": 5
  }
}
```

**OUTPUT:**
```
{
  "_index" : "products",
  "_type" : "_doc",
  "_id" : "101",
  "_version" : 2,
  "result" : "updated",
  "_shards" : {
    "total" : 3,
    "successful" : 1,
    "failed" : 0
  },
  "_seq_no" : 11,
  "_primary_term" : 2
}

```
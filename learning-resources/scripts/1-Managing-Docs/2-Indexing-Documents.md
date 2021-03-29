#Indexing Documents

## Adding Document to a Index
```
POST /products/_doc
    {
      "name": "Coffee Maker",
      "price": 64,
      "in_stock": 10
    }
```
It gives output as follows:
```
{
  "_index" : "products",
  "_type" : "_doc",
  "_id" : "HN3wd3gB1Ode5XT5lBsg",
  "_version" : 1,
  "result" : "created",
  "_shards" : {
    "total" : 3,
    "successful" : 1,
    "failed" : 0
  },
  "_seq_no" : 0,
  "_primary_term" : 1
}
```
Notice shards object , it tells how many shards succeeded or failed. In this case document was started in 3 shards.
Document was added to a primary shard and then to its 2 replica shards.
_id is identified for the doc nd generated automatically if not provided.

#Example to create product with specified ID
## Query
```
PUT /products/_doc/100
   {
     "name": "Playstation",
     "price": 64,
     "in_stock": 10
   }
```

## Output
```
{
  "_index" : "products",
  "_type" : "_doc",
  "_id" : "100",
  "_version" : 1,
  "result" : "created",
  "_shards" : {
    "total" : 3,
    "successful" : 1,
    "failed" : 0
  },
  "_seq_no" : 0,
  "_primary_term" : 1
}

```

Explanation: Adding the first record it has to be POST if index not created. As we dnont have to always create index,
it can be automatically created and the doc would be inserted into it. But its recommended to create an index beforehand.

# Adding Doc to an index which doesnt exist
```
POST /nonexistent-index/_doc
{
  "name":"TestField",
  "price":100
}
```



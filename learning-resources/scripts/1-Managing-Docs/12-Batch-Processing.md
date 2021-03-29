# Batch processing

## Indexing documents

```
POST /_bulk
{ "index": { "_index": "products", "_id": 1 } }
{ "name": "Laptop", "price": 80000, "in_stock": 1 }
{ "create": { "_index": "products", "_id": 2 } }
{ "name": "Mouse", "price": 350, "in_stock": 20 }
```
**Output**
```
{
  "took" : 4316,
  "errors" : false,
  "items" : [
    {
      "index" : {
        "_index" : "products",
        "_type" : "_doc",
        "_id" : "1",
        "_version" : 1,
        "result" : "created",
        "_shards" : {
          "total" : 2,
          "successful" : 1,
          "failed" : 0
        },
        "_seq_no" : 0,
        "_primary_term" : 1,
        "status" : 201
      }
    },
    {
      "create" : {
        "_index" : "products",
        "_type" : "_doc",
        "_id" : "2",
        "_version" : 1,
        "result" : "created",
        "_shards" : {
          "total" : 2,
          "successful" : 1,
          "failed" : 0
        },
        "_seq_no" : 1,
        "_primary_term" : 1,
        "status" : 201
      }
    }
  ]
}
```

The difference is that the "create"
action will fail if the document already exists, which is not the case for the "index"
action. If you use the "index" action, the document will be added if it doesn't
already exist; otherwise it will be replaced.

## Updating and deleting documents
Deletes the product with id 2 i.e  the mouse product and updates the price of laptop i.e product with id 1
```
POST /_bulk
{"update":{"_index":"products","_id":1}}
{"doc":{"price":299}}
{"delete":{"_index":"products","_id":2}}
```

## Specifying the index name in the request path
If all operations are in same index then it can be specified in the url rather than adding key everytime.
```
POST /products/_bulk
{ "update": { "_id": 2 } }
{ "doc": { "price": 129 } }
{ "delete": { "_id": 1 } }
```

## Retrieving all documents

```
GET /products/_search
{
  "query": {
    "match_all": {}
  }
}
```

**When to use BULK API**
* When you need to perform lots of write operations at the same time
    * E.g. when importing data or modifying lots of data
* The Bulk API is more efficient than sending individual write requests
    * A lot of network round trips are avoided


**Points to note:**
* A failed action will not affect other actions
    * Neither will the bulk request as a whole be aborted
* The Bulk API returns detailed information about each action
    * Inspect the items key to see if a given action succeeded
        * The order is the same as the actions within the request
    * The errors key conveniently tells us if any errors occurred
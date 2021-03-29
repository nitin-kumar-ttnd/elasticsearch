# Retrieving Docs by Id
**Query** `GET /products/_doc/100`
**Output**
```
{
  "_index" : "products",
  "_type" : "_doc",
  "_id" : "100",
  "_version" : 1,
  "_seq_no" : 0,
  "_primary_term" : 1,
  "found" : true,
  "_source" : {
    "name" : "Playstation",
    "price" : 64,
    "in_stock" : 10
  }
}
```
Things to note: found key is true and object is found in _source
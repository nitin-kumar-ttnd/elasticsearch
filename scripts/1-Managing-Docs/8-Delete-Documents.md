#Deleting Documents
`DELETE /products/_doc/100`

**Output**
```
{
  "_index" : "products",
  "_type" : "_doc",
  "_id" : "10",
  "_version" : 4,
  "result" : "deleted",
  "_shards" : {
    "total" : 3,
    "successful" : 1,
    "failed" : 0
  },
  "_seq_no" : 16,
  "_primary_term" : 2
}

```

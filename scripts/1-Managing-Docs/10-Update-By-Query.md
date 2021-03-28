# Update by query

## Updating documents matching a query
This query matches all documents in the index. To filter records replace the `match_all` query 
with any query that you would like.

```
POST /products/_update_by_query
{
  "script": {
    "source": "ctx._source.in_stock--"
  },
  "query": {
    "match_all": {}
  }
}
```

We get the count of updated records in the api response as follows:
```
{
  "took" : 223,
  "timed_out" : false,
  "total" : 3,
  "updated" : 3,
  "deleted" : 0,
  "batches" : 1,
  "version_conflicts" : 0,
  "noops" : 0,
  "retries" : {
    "bulk" : 0,
    "search" : 0
  },
  "throttled_millis" : 0,
  "requests_per_second" : -1.0,
  "throttled_until_millis" : 0,
  "failures" : [ ]
}
```

## Ignoring (counting) version conflicts

The `conflicts` key may be added as a query parameter instead, i.e. `?conflicts=proceed`.

```
POST /products/_update_by_query
{
  "conflicts": "proceed",
  "script": {
    "source": "ctx._source.in_stock--"
  },
  "query": {
    "match_all": {}
  }
}
```

## Matches all of the documents within the `products` index

```
GET /products/_search
{
  "query": {
    "match_all": {}
  }
}
```
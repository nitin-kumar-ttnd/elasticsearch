# Delete by query

## Deleting documents that match a given query

```
POST /products/_delete_by_query
{
  "query": {
    "match_all": { }
  }
}
```

Output:
```
{
  "took" : 59,
  "timed_out" : false,
  "total" : 3,
  "deleted" : 3,
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
POST /products/_delete_by_query
{
  "conflicts": "proceed",
  "query": {
    "match_all": { }
  }
}
```
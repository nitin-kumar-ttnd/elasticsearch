# Specifying the result format

## Returning results as YAML

NOTE: Need to debug this why it says error in kibana console.
```
GET /recipe/_search?format=yaml
{
    "query": {
      "match": { "title": "pasta" }
    }
}
```

## Returning pretty JSON

```
GET /recipe/_search?pretty
{
    "query": {
      "match": { "title": "pasta" }
    }
}
```

exporting it as curl and then executing in console gives pretty result.
`curl -XGET "http://localhost:9200/recipe/_search?pretty" -H 'Content-Type: application/json' -d'{  "query": {    "match": {      "title": "pasta"    }  }}'`
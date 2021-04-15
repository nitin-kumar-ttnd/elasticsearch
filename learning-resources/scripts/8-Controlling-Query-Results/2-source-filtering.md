# Source filtering

## Excluding the `_source` field altogether
For scenario where we need to just get ids.
```
GET /recipe/_search
{
  "_source": false,
  "query": {
    "match": { "title": "pasta" }
  }
}
```

## Only returning the `created` field
We can specify one field or array of fields.
```
GET /recipe/_search
{
  "_source": "created",
  "query": {
    "match": { "title": "pasta" }
  }
}
```

## Only returning an object's key

```
GET /recipe/_search
{
  "_source": "ingredients.name",
  "query": {
    "match": { "title": "pasta" }
  }
}
```

## Returning all of an object's keys
 
```
GET /recipe/_search
{
  "_source": "ingredients.*",
  "query": {
    "match": { "title": "pasta" }
  }
}
```

## Returning the `ingredients` object with all keys, __and__ the `servings` field

```
GET /recipe/_search
{
  "_source": [ "ingredients.*", "servings" ],
  "query": {
    "match": { "title": "pasta" }
  }
}
```

## Including all of the `ingredients` object's keys, except the `name` key
When there are lot of keys in ingredients.
```
GET /recipe/_search
{
  "_source": {
    "includes": "ingredients.*",
    "excludes": "ingredients.name"
  },
  "query": {
    "match": { "title": "pasta" }
  }
}
```
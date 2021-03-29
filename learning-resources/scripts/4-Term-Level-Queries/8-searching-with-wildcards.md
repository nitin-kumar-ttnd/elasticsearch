# Searching with wildcards

## Adding an asterisk for any characters (zero or more)

```
GET /products/_search
{
  "query": {
    "wildcard": {
      "tags.keyword": "S*p"
    }
  }
}
```

## Adding a question mark for any single character

```
GET /products/_search
{
  "query": {
    "wildcard": {
      "tags.keyword": "S?p"
    }
  }
}
```

```
GET /products/_search
{
  "query": {
    "wildcard": {
      "tags.keyword": "Veget?ble"
    }
  }
}
```
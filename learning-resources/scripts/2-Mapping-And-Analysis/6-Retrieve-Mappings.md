# Retrieving mappings

## Retrieving mappings for the `reviews` index
```
GET /reviews/_mapping
```

**Output:**
```
{
  "reviews" : {
    "mappings" : {
      "properties" : {
        "author" : {
          "properties" : {
            "dummyField" : {
              "type" : "text",
              "fields" : {
                "keyword" : {
                  "type" : "keyword",
                  "ignore_above" : 256
                }
              }
            },
            "email" : {
              "type" : "keyword"
            },
            "first_name" : {
              "type" : "text"
            },
            "last_name" : {
              "type" : "text"
            }
          }
        },
        "content" : {
          "type" : "text"
        },
        "product_id" : {
          "type" : "integer"
        },
        "rating" : {
          "type" : "float"
        }
      }
    }
  }
}

```

## Retrieving mapping for the `content` field
```
GET /reviews/_mapping/field/content
```

## Retrieving mapping for the `author.email` field
```
GET /reviews/_mapping/field/author.email
```
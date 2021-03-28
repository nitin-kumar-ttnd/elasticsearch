Open Dev Console of Kibana
http://127.0.0.1:5601/app/dev_tools#/console

# Delete an Index
DELETE name-of-the-index
DELETE /pages

# Creating Indices
## creates with default settings
`PUT /products`

## Creating with customised settings:
```
PUT /products
{
  "settings" : {
    "number_of_shards": 2,
    "number_of_replicas": 2
  }
}
```
# Listing All Indices
`GET /_cat/indices`

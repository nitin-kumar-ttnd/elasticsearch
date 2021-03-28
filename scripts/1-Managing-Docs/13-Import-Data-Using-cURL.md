# Importing data with cURL

## Importing data into local cluster
--data-binary is specifying the file name so make sure you are in the same folder where the file `products-bulk.json` is
In this repo, the location of file is [here](../../resources/products-bulk.json)
```
curl -H "Content-Type: application/x-ndjson" -XPOST http://localhost:9200/products/_bulk --data-binary "@products-bulk.json"
```

## Importing data into Elastic Cloud 
```
curl -H "Content-Type: application/x-ndjson" -XPOST -u username:password https://elastic-cloud-endpoint.com:9243/products/_bulk --data-binary "@products-bulk.json"
```

## See the status of shards here
`GET /_cat/shards?v`
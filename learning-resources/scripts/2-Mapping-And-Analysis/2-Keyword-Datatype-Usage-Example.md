# Working of `keyword` data type

## Testing the `keyword` analyzer
```
POST /_analyze
{
  "text": "This sentence wont be tokenized.",
  "analyzer": "keyword"
}
```
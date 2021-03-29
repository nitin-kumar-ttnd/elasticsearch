# Using the Analyze API

## Analyzing a string with the `standard` analyzer
Words are extracted, special symbols are removed and words are turned lowercase.
```
POST /_analyze
{
"text":"This text would be analyzed using the standard analyzer. Here are some differnt symbols , .  - ! @ # $ % ^ & * ( )",
"analyzer":"standard"}
```

## Building the equivalent of the `standard` analyzer
```
POST /_analyze
{
  "text": "This text would be analyzed using the standard analyzer. Here are some differnt symbols , .  - ! @ # $ % ^ & * ( )",
  "char_filter": [],
  "tokenizer": "standard",
  "filter": ["lowercase"]
}
```
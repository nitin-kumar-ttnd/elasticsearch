# Matching phrases

## The order of terms matters
Matches sequences of words
```
GET /recipe/_search
{
  "query": {
    "match_phrase": {
      "title": "spaghetti puttanesca"
    }
  }
}
```
Switching he terms would yield no result. so the sequence matters when we use match_phrase.
```
GET /recipe/_search
{
  "query": {
    "match_phrase": {
      "title": "puttanesca spaghetti"
    }
  }
}
```
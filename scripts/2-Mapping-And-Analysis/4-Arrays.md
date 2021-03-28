#Arrays
* There is no such thing as an array data type.
* Any field may contain zero or more values
* No configuration or mapping needed
* Simply supply an array when indexing a document
* Arrays may contain nested arrays
* Arrays are flattened during indexing
* [ 1, [ 2, 3 ] ] becomes [ 1, 2, 3 ]

## Constraints with Arrays
* Array values should be of the same data type
* Coercion only works for fields that are already mapped
* If creating a field mapping with dynamic mapping, an array must contain the same data type

## Arrays of strings are concatenated when analyzed
```
POST /_analyze
{
  "text": ["Strings are simply", "merged together."],
  "analyzer": "standard"
}
```
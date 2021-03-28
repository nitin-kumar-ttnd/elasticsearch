# Optimistic Concurrency Control

```
POST /products/_update/100?if_primary_term=1&if_seq_no=9
{
  "doc": {
    "in_stock": 123
  }
}
```
If the primary term and seq no doesnt match, an exception would be thrown in result.
We need to handle this situation at the application level (as follows):
* Retrieve the doc again
* User _primary_term and _seq_no for a new update request
* Remember to perform any calculations that use field values again.
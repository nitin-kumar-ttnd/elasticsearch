#Replacing documents
```
PUT /products/_doc/100
{
  "name": "Toaster",
  "price": 79,
  "in_stock": 4
}
```
In this case if we change any field name and re-execute the command, 
the old fields would be gone  and only new fields would be there hereby showing that it is 
actually replacing docs.
For example change price to amount then the new record will have amount and not price in doc.
##Update Stock Field By One
```
POST /products/_update/100
 {
   "script": {
     "source": "ctx._source.in_stock++"
   }
 }
``` 

##Assing Value to field
```
 POST /products/_update/100
 {
   "script": {
     "source": "ctx._source.in_stock = 10"
   }
 }
 ```
 
 ##Subtract a param
 ```
 POST /products/_update/100
 {
   "script": {
     "source": "ctx._source.in_stock -= params.quantity",
     "params": {
       "quantity": 4
     }
   }
 }
 ```

##Dont update if field is already zero
```
 POST /products/_update/100
 {
   "script": {
     "source": """
     if(ctx._source.in_stock == 0) {
       ctx.op='noop';
     }
     ctx._source.in_stock--;
     """
   }
 }
 ```
 ##Update only if greater than zero (It will always return status updated)
 ```
 POST /products/_update/100
 {
   "script": {
     "source": """
     if(ctx._source.in_stock > 0) {
     ctx._source.in_stock--;
     }
     """
   }
 }
 ```
 ##Delete product if count reaches zero
 ```
 POST /products/_update/100
 {
   "script": {
     "source": """
     if(ctx._source.in_stock <= 1) {
       ctx.op='delete';
     }
     ctx._source.in_stock--;
     """
   }
 }
```
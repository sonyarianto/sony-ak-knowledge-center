Update in loop for specific data element.
```aql
FOR data IN train
UPDATE data WITH { color:LOWER(data.color) } IN train
```

Just imagine below XPath sample. It will get odd `<tr>` from a table markup and get only first 10 data.

```
((//table[@width='500'])[1]//table[@width='100%'])[1]//tr[position() mod 2 = 1 and position() <= 20]
```

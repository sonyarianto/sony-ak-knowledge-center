```sql
SELECT A.*
FROM A LEFT JOIN B ON A.BAND = B.HATE
WHERE B.HATE IS NULL;
```

Read the detail on http://stackoverflow.com/questions/15890367/select-from-table-a-which-does-not-exist-in-table-b

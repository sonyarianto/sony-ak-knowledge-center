```sql
SELECT fields FROM table WHERE DATE_SUB(CURDATE(),INTERVAL 30 DAY) >= date_field;
```

Notes:
`fields` is fields list.
`table` is table name.
`date_field` is date field on the table.

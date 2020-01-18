```
mysqldump -uroot -h DATABASE_HOST -p --column-statistics=0 --databases --triggers --routines --events your_database_name > your_database_name.sql
```

`--column-statistics=0` means disable GTID

`--databases` means add CREATE DATABASE line

`--triggers --routines --events` means include triggers, routines and events if available

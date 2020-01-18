```
mysqldump -uroot -h DATABASE_HOST -p --column-statistics=0 --triggers --routines --events your_database_name > your_database_name.sql
```

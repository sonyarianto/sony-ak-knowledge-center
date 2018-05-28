Do this.
```mysql
REPLACE(REPLACE(your_mysql_column, '\n', ' '), '\r', ' ')
```
It will replace newline character with a space.

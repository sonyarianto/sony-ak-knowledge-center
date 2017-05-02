My experience just login to AWS RDS console, select RDS instance and select Modify menu then reset the master password.

If you want to know how many days it will expired, just login to MySQL via command line and type this.

```sql
mysql> SHOW GLOBAL VARIABLES LIKE 'default_p%';
+---------------------------+-------+
| Variable_name             | Value |
+---------------------------+-------+
| default_password_lifetime | 360   |
+---------------------------+-------+
1 row in set (0.00 sec)
```

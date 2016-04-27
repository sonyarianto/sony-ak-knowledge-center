Go to `MySQL` console and type this.
```sql
SELECT @@sql_mode;
```
It will return current state of SQL modes. On mine the output is like below.
```
+-------------------------------------------------------------------------------------------------------------------------------------------+
| @@sql_mode                                                                                                                                |
+-------------------------------------------------------------------------------------------------------------------------------------------+
| ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION |
+-------------------------------------------------------------------------------------------------------------------------------------------+
1 row in set (0.02 sec)
```
So to disable new behaviour of `GROUP BY` after `MySQL` version `5.7.5` just remove the `ONLY_FULL_GROUP_BY` part.

Go to `/etc/my.cnf` and add this config.
```
sql_mode=STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION
```
Then restart `MySQL` like below
```
service mysqld restart
```

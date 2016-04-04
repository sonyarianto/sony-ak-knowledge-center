Sometimes when you want to change the password of MySQL and this error appear.
```
ERROR 1819 (HY000): Your password does not satisfy the current policy requirements
```
Workaround is setting `/etc/my.conf` using `validate-password = off`

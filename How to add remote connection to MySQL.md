1. Create user % for root on MySQL.

```
CREATE USER 'root'@'%' IDENTIFIED BY 'mypass';
```
Then
```
GRANT ALL ON *.* TO 'root'@'%';
```
Then
```
FLUSH PRIVILEGES;
```

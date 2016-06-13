Let’s start by making a new user within the MySQL shell:
```sql
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
```
Therefore, the first thing to do is to provide the user with access to the information they will need.
```sql
GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost';
```
or do this
```sql
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' WITH GRANT OPTION;

CREATE USER 'username'@'%' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON *.* TO 'username'@'%' WITH GRANT OPTION;

FLUSH PRIVILEGES;
```

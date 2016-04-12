Let’s start by making a new user within the MySQL shell:
```sql
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
```
Therefore, the first thing to do is to provide the user with access to the information they will need.
```sql
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
```

Scenario I have EC2 with Linux AMI2. I need MySQL running on that server.

I do this.

1. Setup Docker
2. Setup Docker Compose
3. Here is the docker-compose.yml (It will expose MySQL server port 3306 to host machine)

```
version: '3.1'

services:

  db:
    image: mysql
    command: --default-authentication-plugin=mysql_native_password
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: my_root_password_here
    ports:
      - 3306:3306
```

4. Run it with `docker-compose up -d`
5. Run `docker ps` to see the process already run
6. Install MySQL client by typing `sudo yum install mysql`
7. Type `mysql` to check the command available
8. Now connect to MySQL server by type this command

```
mysql -uroot --protocol=tcp -p
```
Type your MySQL root password and then voila, you can login now.

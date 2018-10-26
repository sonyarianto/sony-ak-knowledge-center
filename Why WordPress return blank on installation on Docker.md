I have WordPress installed manual and I run it using Docker php:56-apache image.

But when install it (on installation screen) it return 500 error.

Solution is simple.

Install mysql extension, add it to your Dockerfile. At first I don't believe it, since I checked there is mysqlnd, but after I tried and it works.

```
RUN docker-php-ext-install mysql
```

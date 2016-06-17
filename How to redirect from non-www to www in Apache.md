Edit your virtualhost config like below.
```
RewriteEngine On
RewriteCond %{HTTP_HOST} !^www\.
RewriteRule .* http://www.%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

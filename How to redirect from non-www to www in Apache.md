Edit your virtualhost config like below.

Example 1
```
RewriteEngine On
RewriteCond %{HTTP_HOST} !^www\.
RewriteRule .* http://www.%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

Example 2
```
RewriteEngine On
RewriteCond %{HTTP_HOST} ^yourdomain.com [NC]
RewriteRule ^(.*)$ http://www.yourdomain.com/$1 [L,R=301]
```

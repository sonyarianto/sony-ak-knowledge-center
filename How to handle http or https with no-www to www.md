This is should be on your `.htaccess`

```
RewriteCond %{HTTPS} !on [OR]
RewriteCond %{HTTP_HOST} !^www\.
RewriteRule (.*) https://www.yourdomain.com%{REQUEST_URI} [L,R=301]
```

After that test with your browser with clear cache and also test with redirect checker such as http://www.redirect-checker.org

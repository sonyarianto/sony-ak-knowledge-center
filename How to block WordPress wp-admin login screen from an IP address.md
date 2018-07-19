```
RewriteEngine on
RewriteCond %{REQUEST_URI} ^(.*)?wp-login\.php(.*)$ [OR]
# Use below if non behind proxy
#RewriteCond %{REMOTE_ADDR} !^111\.111\.111\.111
# Use below if behind proxy
RewriteCond %{HTTP:X-FORWARDED-FOR} !^111\.111\.111\.111
RewriteRule ^(.*)$ - [R=403,L]
```

I know `%{HTTP:X-FORWARDED-FOR}` by reading this https://serverfault.com/questions/329860/htaccess-rewritecond-for-remote-addr-while-behind-load-balancer

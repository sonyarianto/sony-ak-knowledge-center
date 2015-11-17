Just add this to your `httpd.conf` on Apache.

~~~
ExpiresActive On
ExpiresByType image/gif "access 1 month"
ExpiresByType image/jpg "access 1 month"
ExpiresByType image/jpeg "access 1 month"
ExpiresByType image/png "access 1 month"
ExpiresByType text/css "access 1 month"
ExpiresByType text/js "access 1 week"
ExpiresByType application/javascript "access 1 week"
~~~

Above is just an example, you can improvise based on your requirements.

References:
- https://httpd.apache.org/docs/2.2/mod/mod_expires.html

Just read here https://www.digitalocean.com/community/tutorials/how-to-set-up-password-authentication-with-apache-on-ubuntu-14-04

or the concept is

1. `sudo htpasswd -c .htpasswd your_username` I assume you type this on folder `/etc/httpd`
2. If you want to add other user, just remove the `-c` option
3. See below config on Apache. Basically see the `Directory` section.
```
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined

    <Directory "/var/www/html">
        AuthType Basic
        AuthName "Restricted Content"
        AuthUserFile /etc/httpd/.htpasswd
        Require valid-user
    </Directory>
</VirtualHost>
```

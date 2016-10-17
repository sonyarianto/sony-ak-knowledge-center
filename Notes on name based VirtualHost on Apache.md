Suppose you have web server and the default DocumentRoot already installed on an IP address (let say A setup).

Next you want to use that IP to serve a domain on differrent DocumentRoot folder (let say B setup)

Then you should create VirtualHost for your previous setup (A setup) like below.

```
<VirtualHost *:80>
  ServerAdmin sony@sony-ak.com
  DocumentRoot /var/www/a-setup/html
  <Directory "/var/www/a-setup/html">
    Options Indexes FollowSymLinks
    AllowOverride All
    Order allow,deny
    Allow from all
  </Directory>
</VirtualHost>
```

then below that create for (B setup) like below

```
<VirtualHost *:80>
     ServerAdmin sony@sony-ak.com
     DocumentRoot /var/www/b-setup/html
     ServerName www.your-domain.com
     ServerAlias your-domain.com
     ErrorLog logs/b-setup.error_log
     CustomLog logs/b-setup.error_log common
     <Directory "/var/www/b-setup/html">
       Options Indexes FollowSymLinks
       AllowOverride All
       Order allow,deny
       Allow from all
     </Directory>
</VirtualHost>
```
Then before (A setup) VirtualHost above add below directive.
```
NameVirtualHost *:80
```

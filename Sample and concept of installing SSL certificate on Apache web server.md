On file `httpd.conf` or `ssl.conf` look for this directive.
```
SSLCertificateFile /[path]/[server certificate file]
```
```
SSLCertificateKeyFile /[path]/[private key file]
```
```
SSLCertificateChainFile /[path]/[intermediate certificate file]
```
Note: Some versions of `Apache` will not accept the `SSLCertificateChainFile` directive. Try using `SSLCACertificateFile` instead.

Below is the sample.
```
<VirtualHost [IP ADDRESS]:443>
ServerAdmin [admin email address]             
DocumentRoot /[path]/[to document root]
ServerName [site address]
ErrorLog /path/[error log]
SSLEngine on
SSLProtocol all
SSLCertificateFile /[path]/[server certificate file]
SSLCertificateKeyFile /[path]/[private key file]
SSLCertificateChainFile /[path]/[intermediate certificate file]
ServerPath /[path]
<Directory "/path]">
</Directory>
</VirtualHost>
```

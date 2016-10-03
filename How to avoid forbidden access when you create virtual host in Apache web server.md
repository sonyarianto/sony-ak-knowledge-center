As mentioned in https://www.petefreitag.com/item/793.cfm

* Make sure it's not denied by Apache
```
<Directory /path/to/webroot>
    Order allow,deny
    Allow from all
</Directory>
```

* If Running Security Enhanced Linux (SELinux)

Another possibility for this error is that you are running SELinux (Security Enhanced Linux), inwhich case you need to use chcon to apply the proper security context to the directory. One easy way to do this is to copy from a directory that does work for example /var/www/

```bash
chcon -R --reference=/var/www /path/to/webroot
```

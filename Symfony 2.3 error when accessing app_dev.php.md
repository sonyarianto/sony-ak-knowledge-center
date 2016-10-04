Just open `app_dev.php` and comment the lines below.

```php
 header('HTTP/1.0 403 Forbidden');
 exit('You are not allowed to access this file. Check '.basename(__FILE__).' for more information.');
```

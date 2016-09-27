```php
$regex = '/https?\:\/\/[^\" ]+/i';
$string = "lorem ipsum http://google.com lorem ipusm dolor http://yahoo.com/something";
preg_match($regex, $string, $matches);
echo $matches[0];
```

We have a string like this `/international/europe/uefa-champions-league/20182019/final/r48409`

And we want to get this substring `r48409`

This is the PHP code to achieve that.

```php
$b = '/international/europe/uefa-champions-league/20182019/final/r48409';
echo substr($b, strrpos($b, '/') + 1);
```

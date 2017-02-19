```php
$re = '/alt\s*=\s*"(.+?)"/i';
$str = '<img class="my_class" src="/images/image.png" alt="This is my alt" title="This is my title">';

preg_match($re, $str, $matches);

// Print the entire match result
print_r($matches);
```

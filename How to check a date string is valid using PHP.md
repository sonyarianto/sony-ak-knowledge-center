```php
$str1 = '2017-03-21 09:09:00';
$str2 = '2017-03-21 09:09:00 +';

if (($timestamp = strtotime($str1)) === false) {
    echo 'str1 is not valid date';
} else { echo 'str1 is valid date'; }
echo "\n";
if (($timestamp = strtotime($str2)) === false) {
    echo 'str2 is not valid date';
} else { echo 'str2 is valid date'; }
```

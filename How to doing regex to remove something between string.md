```php
$re = '/<!--[\s\S]+?-->/';
$str = '<!--
this is very
very cool
-->';
$subst = '';

$result = preg_replace($re, $subst, $str, 1);

echo "The result of the substitution is ".$result;
```

It will remove everything between `<!--` and `-->` including those string as well.

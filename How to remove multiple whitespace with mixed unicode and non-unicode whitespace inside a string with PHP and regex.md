```php
$re = '/(\s+)/u';
$str = '&#x1F30D;&#x1F4FA;&#x231A;&#xFE0F; Pedoman stasiun TV dunia yg menayangkan laga liga melawan Leganes   #ForçaBarça';
$subst = ' ';

$result = preg_replace($re, $subst, $str);

echo "The result of the substitution is ".$result;
```

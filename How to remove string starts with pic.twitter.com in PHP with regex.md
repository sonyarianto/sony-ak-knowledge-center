```php
$re = '/(pic\.twitter\.com\/[0-9,a-z,A-Z]*)/';
$str = '&#x1F3A5; Leo #Messi menujukan keperdulianya lewat video terbaru ini  &#x1F535;&#x1F534; Tonton di http://ow.ly/SunY3092Ik2 pic.twitter.com/z8DESIfeBo';
$subst = '';

$result = preg_replace($re, $subst, $str);

echo "The result of the substitution is ".$result;
```

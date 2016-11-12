Please see below sample.

```php
$re = '/(Berita Liga Inggris: |Berita Liga Spanyol: )/';
$str = 'Berita Liga Inggris: Masa Depan Tammy Abraham di Chelsea Belum Jelas dan Berita Liga Spanyol: Masa Depan Tammy Abraham di Chelsea Belum Jelas';
$subst = '';

$result = preg_replace($re, $subst, $str);

echo "The result of the substitution is ".$result;
```

Tested using www.regex101.com

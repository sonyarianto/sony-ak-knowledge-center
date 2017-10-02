```php
$list = array (
    array('Sony AK', 'Jakarta', 'sony@sony-ak.com', '40'),
    array('Elon Musk', 'Los Angeles', 'elon@musk.com', 55),
    array('Bill Gates', 'Seattle', 'bill@gates.com', 67)
);

$fp = fopen('file.csv', 'w');

foreach ($list as $fields) {
    fputcsv($fp, $fields);
}

fclose($fp);
```

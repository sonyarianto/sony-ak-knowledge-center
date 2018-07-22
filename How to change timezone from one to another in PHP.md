```php
<?php
$date = new DateTime('2000-01-01', new DateTimeZone('Pacific/Nauru'));
echo $date->format('Y-m-d H:i:sP') . "\n";

$date->setTimezone(new DateTimeZone('Pacific/Chatham'));
echo $date->format('Y-m-d H:i:sP') . "\n";
```

Or read here https://stackoverflow.com/questions/3905193/convert-time-and-date-from-one-time-zone-to-another-in-php

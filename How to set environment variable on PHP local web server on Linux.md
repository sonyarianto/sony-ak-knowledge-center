```
ANU=HAHAHA php -d variables_order=EGPCS -S 0.0.0.0:8000 -t public/
```

later we can get the value on PHP like below.

```php
<?php
  echo getenv('ANU');
```

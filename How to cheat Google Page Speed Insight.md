```php
<?php if(!isset($_SERVER['HTTP_USER_AGENT']) || stripos($_SERVER['HTTP_USER_AGENT'], 'Speed Insights') === false) ?>
  // your analytics code here or any code that you don't want visible to Google Page Speed Insight
<?php } ?>
```

```php
<?php
$url = 'https://bolabanget.id/kamprettttt';

$handle = curl_init($url);
curl_setopt($handle,  CURLOPT_RETURNTRANSFER, TRUE);
curl_setopt($handle, CURLOPT_NOBODY, 1); // and *only* get the header 
/* Get the HTML or whatever is linked in $url. */
$response = curl_exec($handle);
/* Check for 404 (file not found). */
$httpCode = curl_getinfo($handle, CURLINFO_HTTP_CODE);

echo $httpCode; // it should be 404
```

But if domain not exists or URL not valid then it will return 0 and later you can check with 
```php
echo curl_error($handle);
```

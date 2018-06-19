```php
$aContext = array(
    'http' => array(
        'proxy' => 'tcp://192.168.0.2:3128',
        'request_fulluri' => true,
        'header' => array('User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.13; rv:60.0) Gecko/20100101 Firefox/60.0')
    ),
);
$cxContext = stream_context_create($aContext);

$sFile = file_get_contents("http://www.google.com", False, $cxContext);
```

See this example.

```php
$context = stream_context_create(array('http' => array('header' => array('User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.13; rv:60.0) Gecko/20100101 Firefox/60.0')),
				                               'ssl'  => array('verify_peer' => false, 'verify_peer_name' => false)));
```

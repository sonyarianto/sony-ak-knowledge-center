Include
```php
use Symfony\Component\HttpFoundation\Request;
```

then

```php
$request     = $this->getRequest();
$region1Id   = $request->query->get('region1_id'); // get query string data region1_id
```

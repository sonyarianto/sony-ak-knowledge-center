You can get the current URL in Twig like this:
```php
{{ app.request.schemeAndHttpHost ~ app.request.requestUri }}
```

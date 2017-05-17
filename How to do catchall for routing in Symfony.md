```yml
catch_all:
    path:     /{catchall}
    defaults:
        _controller: YourProjectBundle:Index:catchAll
    requirements:
        catchall: ".+"
```

and in Controller do this.

```php
class DefaultController extends Controller
{
    public function indexAction(Request $request) {
      // do something here baby
    }
```

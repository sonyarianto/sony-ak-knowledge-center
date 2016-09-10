For parsing RSS feed better use this.

```php
$xmlDoc = new DOMDocument();
@$xmlDoc->loadXML($curlData); // for RSS just use loadXML instead of loadHTML
```

If you want to remove everything, link and after the link, like via thing in your example, the below may help you:

```php
$string = "The Third Culture: The Frontline of Global Thinkinghttp://is.gd/qFioda;via @edge";
$regex = "@(https?://([-\w\.]+[-\w])+(:\d+)?(/([\w/_\.#-]*(\?\S+)?[^\.\s])?).*$)@";
echo preg_replace($regex, ' ', $string);
```

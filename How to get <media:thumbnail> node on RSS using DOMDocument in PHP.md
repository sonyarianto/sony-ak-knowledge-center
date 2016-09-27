You are dealing with namespace.

On the header of XML usually there is like below.

```xml
<channel xmlns:media="http://search.yahoo.com/mrss/">
```

On XML document usually there is like below.

```xml
<media:thumbnail url="https://apac-webapp-assets.ballball.com/prod/uploads/articles/articleimageversion/720p-Serge%20Aurier%20two%20months%20jail.jpg" width="460" height="302"></media:thumbnail>
```

In PHP you can do this.

```php
$imageMedium 	= $eachXpathElement->getElementsByTagNameNS('http://search.yahoo.com/mrss/', 'thumbnail')->item(0)->getAttribute('url');
```

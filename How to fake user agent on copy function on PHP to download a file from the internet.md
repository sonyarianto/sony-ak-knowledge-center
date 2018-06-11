Just read it here https://techglimpse.com/fix-http-403-forbidden-php-copy/

Or do this.

```php
<?php
 $context = stream_context_create(array(
 'http' => array(
 'header' => array('User-Agent: Mozilla/5.0 (Windows; U; Windows NT 6.1; rv:2.2) Gecko/20110201'),
 ),
 ));
 $imageURL = "https://www.domain.net/images/commercial-wordPress-theme1.jpg";
 copy($imageURL,'sample.jpg', $context);
```

See below example.

```php
  $xPathQuery = $xPathDoc->query("//div[@id='something']//div");
  
  if($xPathQuery->length == 0) {
    $isEntryFound = false;
  } else {
    $isEntryFound = true;
  }
  
  if($isEntryFound) {
    foreach($xPathQuery as $eachXpathElement) {
      $data 	= $xPathDoc->query("(.//span[@class='something-happen'])[1]", $eachXpathElement);
      $myDesiredData = utf8_decode(trim($data->item(0)->nodeValue));
    }
  }
```

Please look at the code fragment below.

```php
$data = $xPathDoc->query("(.//td)[2]/node()", $eachXpathElement);
			
if($data->length > 0) {
  $rawEventName = "";
	foreach($data as $eachNode) {
		$rawEventName = $rawEventName . $eachNode->ownerDocument->saveHTML($eachNode); // this is the key of success hahahaha
	}
	$rawEventName = trim($rawEventName);
}

$eventName  = str_replace(array('<br>'), ' ', $rawEventName);
```

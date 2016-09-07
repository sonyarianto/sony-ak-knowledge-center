Case 1
```json
{"commands":[{"name":"updateContainer","parameters":{"content":"Content Here"}}]}
```
The PHP code to read content is:
```php
$obj = json_decode('{"commands":[{"name":"updateContainer","parameters":{"content":"Content Here"}}]}');
echo $obj->{'commands'}[0]->{'parameters'}->{'content'};
```

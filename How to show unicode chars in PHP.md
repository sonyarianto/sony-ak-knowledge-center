Sometimes when you echo a string that contains unicode characters, PHP will still show normal chars. So to make sure what character is that, just do this.

```php
$shortContent = 'some string that contains unicode chars';
echo json_encode($shortContent);
```

If you are lucky then it will show the unicode characters that hidden beneath your string.

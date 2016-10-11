The trim function doesn't know about Unicode white spaces. You could try this:
```php
preg_replace('/^\p{Z}+|\p{Z}+$/u', '', $str);
```
As taken from: http://stackoverflow.com/questions/4166896/trim-unicode-whitespace-in-php-5-2

Otherwise, you can do a bin2hex() to find out what characters are being added at the front.

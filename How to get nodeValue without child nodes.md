Suppose you have markup like below.
```html
<foo>
  a
  <bar> b </bar>
</foo>
```
and you want only get `a`.

Just use `firstChild`:
```php
$foo->firstChild->textContent;
```



HTML Scenario

```html
<p>This is the best <span>programmer</span></p>
```

Usually if you target node `p` with nodeValue it will get string `This is the best programmer` without `<span>`.

If you want to get `<span>` as well, do this.

Sample 1
```php
$content = $nodePath->c14n();
```

Sample 2 (recommended)
```php
$content = $nodePath->ownerDocument->saveHTML($nodePath);
```

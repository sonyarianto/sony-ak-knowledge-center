When you doing scraping, the Curl are doing well on encoding but the DOMDocument is doing encoding wrongly. So remember this recipe.

```php
// Create a DOMDocument instance 
$doc = new DOMDocument();

// The fix: mb_convert_encoding conversion
$doc->loadHTML(mb_convert_encoding($content, 'HTML-ENTITIES', 'UTF-8'));
```

It will make everything works well.

```php
<?php
  $imageUri = 'http://rakyatsulsel.com/wp-content/uploads/2017/08/Romelu-Lukaku-Cetak-Gol-Debut-Liga-696x464.jpg';
  $pathParts = pathinfo($imageUri);
  $filePart = $pathParts['basename'];

  copy($imageUri, __DIR__ . '/' . $filePart);
```

Suggestions:
* Change `$filePart` to slug-based file name
* Use Flysystem? (If target folder not found)
* Target path must be already exists

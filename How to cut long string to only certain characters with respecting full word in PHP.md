Just use `wordwrap` function in PHP and later use your imagination.

Example:
```php
// make title max 60 chars respecting full word
$newTitle = wordwrap($title, 60, "<br>");
$arrNewTitle = explode("<br>", $newTitle);
$title = $arrNewTitle[0] . "...";
```

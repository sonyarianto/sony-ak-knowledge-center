```php
$string = 'page_competition_1_block_competition_matches_summary_5_match-2758658';
$tmp = explode('-', $string);
echo array_pop($tmp);
// it will print 2758658
```

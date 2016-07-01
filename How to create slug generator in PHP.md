```php
function slugGenerator($string) {
  // unwanted:  {UPPERCASE} ; / ? : @ & = + $ , . ! ~ * ' ( )
  $string = strtolower($string);
  
  // strip any unwanted characters
  $string = preg_replace("/[^a-z0-9_\s-]/", "", $string);
  
  // clean multiple dashes or whitespaces
  $string = preg_replace("/[\s-]+/", " ", $string);
  
  // convert whitespaces and underscore to dash
  $string = preg_replace("/[\s_]/", "-", $string);
  
  return $string;
}
```

```php
<?php
  $re = '/<img .*?>/';
  $str = '<body>
          OK this is the body that contains image
          <img src="/img/hahah.jpg" alt="ok">
          <span>ok</span>
          </body>';
  $subst = '';

  $result = preg_replace($re, $subst, $str);

  echo "The result of the substitution is ".$result;
```

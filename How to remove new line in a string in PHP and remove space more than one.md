Just do this.

~~~
  $myString = str_replace(array("\r\n", "\r", "\n"), "", trim($myString));
  $myString = preg_replace('!\s+!', ' ', $myString);
~~~

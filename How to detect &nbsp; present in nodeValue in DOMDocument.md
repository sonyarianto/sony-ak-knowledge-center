Just see below PHP fragment.
~~~php
  // check if nodeValue is &nbsp;
  if($domElement->nodeValue == "\xC2\xA0") {
    // do something
  }
~~~
When you want to compare nodeValue for being &nbsp;, you need to know two things:

* `&nbsp;` is a HTML entity that represents a specific character, here the non-breaking space which could be formally specified as Unicode Character `'NO-BREAK SPACE'` (U+00A0).
* The DOMDocument library uses `UTF-8` as character encoding when giving or accepting string values.

With this general information at hand, it's easy to solve your problem. As `&nbsp;` stands for `NO-BREAK SPACE` (U+00A0) and as `DOMElement::nodeValue` returns the contents as `UTF-8` encoded string and as `NO-BREAK SPACE` in `UTF-8` is `"\xC2\xA0"` in PHP you can simply compare it.

Suppose there is markup.

~~~html
<article>
  <ul>
    <li>Data 1</li>
    <li>E-mail: test@domain1.com</li>
  </ul>
</article>
<article>
  <ul>
    <li>Data 2</li>
    <li>E-mail: test@domain1.com</li>
  </ul>
</article>
~~~

Now we want to get data from `li` that start with `E-mail`.

~~~xpath
//li[starts-with(text(),'E-mail:')]
~~~

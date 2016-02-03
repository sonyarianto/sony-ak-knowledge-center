You can also provide a list of templates that are checked for existence before inclusion. The first template that exists will be included:
~~~
{% include ['page_detailed.html', 'page.html'] %}
~~~
If ignore missing is given, it will fall back to rendering nothing if none of the templates exist, otherwise it will throw an exception.

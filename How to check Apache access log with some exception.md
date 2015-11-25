Suppose you want to display access log that not from `Googlebot` and `YandexBot`.

~~~
tail -F /var/log/httpd/front_prod.access_log | awk '!/Googlebot/ && !/YandexBot/'
~~~

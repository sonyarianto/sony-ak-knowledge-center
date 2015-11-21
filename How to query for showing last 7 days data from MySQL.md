Suppose we have a MySQL table with `date` or `datetime` type field and you want to display data just last 7 days from now. You can add below criteria on your SQL.

~~~sql
...
WHERE DATE(your_date_field) > (NOW() - INTERVAL 7 DAY)
...
~~~

Now even you can modify it to show last n days data.

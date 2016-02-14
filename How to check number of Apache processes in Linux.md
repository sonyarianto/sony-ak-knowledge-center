Keep an eye on the number of Apache processes, and the total RAM used. Here's a command that wraps this into a single output that updates every second:
~~~bash
watch -n 1 "echo -n 'Apache Processes: ' && ps -C apache2 --no-headers | wc -l && free -m"
~~~
or
~~~bash
watch -n 1 "echo -n 'Apache Processes: ' && ps -C httpd --no-headers | wc -l && free -m"
~~~

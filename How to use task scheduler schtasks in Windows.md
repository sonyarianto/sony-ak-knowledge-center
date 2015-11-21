In Windows there is `schtasks` command to do similar like `cron` in Linux/Unix. Here is one of the example.

##Run command every 20 minute

~~~
schtasks /create /sc minute /mo 20 /tn "This is task name" /tr "php execute-me.php"
~~~

It will run command `php execute-me.php` every 20 minutes since that command started.

For reference please have a look at below reference.

Reference:
- https://technet.microsoft.com/en-us/library/cc725744.aspx

Just run this command.

~~~
visudo
~~~

Find the following code:

~~~
## Allow root to run any commands anywhere
root ALL=(ALL) ALL
~~~

In this case, we're granting root privileges to the user `youruser`. Add the following below that code:

~~~
youruser ALL=(ALL) ALL
~~~

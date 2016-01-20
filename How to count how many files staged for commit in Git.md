If you want something a script can use:
~~~
git diff --cached --numstat | wc -l
~~~
If you want something human readable:
~~~
git diff --cached --stat
~~~

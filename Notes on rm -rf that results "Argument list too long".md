#Option 1:
~~~
for x in `ls`; do rm $x; done
~~~
This is a pretty easy option, Using x for loop every line of output from ls executes an rm.

#Option 2:
~~~
ls | xargs rm
~~~

This will take the output of ls and send it to the command xargs which will then breakup the output and run multiple rm commands with smaller sets of arguments.

#Option 3:
~~~
find ./ -maxdepth 1 -type f -exec rm {} \;
~~~

You could also use find with the -exec flag but this can be a little dangerous, if you don't have the -maxdepth option find will also delete files in sub-directories. You may or may not want that.

With that said in certain situations Option 2 and 1 are also dangerous so be careful whenever you are performing file options like the above.

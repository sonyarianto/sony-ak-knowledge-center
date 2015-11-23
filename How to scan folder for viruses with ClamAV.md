To check all files on the computer, displaying the name of each file:

~~~
clamscan -r /
~~~

To check all files on the computer, but only display infected files and ring a bell when found:

~~~
clamscan -r --bell -i /
~~~

To check files in the all users home directories:

~~~
clamscan -r /home
~~~

To check files in the USER home directory and move infected files to another folder:

~~~
clamscan -r --move=/home/USER/VIRUS /home/USER
~~~

To check files in the USER home directory and remove infected files (WARNING: Files are gone.):

~~~
clamscan -r --remove /home/USER
~~~

To see more options:

~~~
clamscan --help
~~~

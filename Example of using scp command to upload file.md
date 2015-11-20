Suppose you have remote hosts using SSH with details like below:
~~~
Host IP: 111.222.113.123
Port: 45433
Username: sony
Identity file (with passphrase): /c/Users/sonyak/id_rsa_server
Local file: web/a.txt
Remote path: /remote/folder/
~~~

Suppose you want to copy `Local file` above to `Remote path`

~~~
scp -P 45433 -i /c/Users/sonyak/id_rsa_server web/a.txt sony@111.222.113.123:/remote/folder/web/a.txt
~~~

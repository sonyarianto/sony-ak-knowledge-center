First thing.

~~~
yum update && yum upgrade
~~~

then if you want to install Apache do this.

~~~
yum install httpd
~~~

then set the firewall

~~~
firewall-cmd --permanent --add-service=http
~~~

then

~~~
firewall-cmd --reload
~~~

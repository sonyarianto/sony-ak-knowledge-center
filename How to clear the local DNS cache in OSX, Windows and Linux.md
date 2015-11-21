**OSX 10.11.0**

~~~
sudo killall -HUP mDNSResponder
~~~

**OSX 10.10.4**

~~~
sudo killall -HUP mDNSResponder
~~~

**OSX 10.10.0 - 10.10.3**

~~~
sudo discoveryutil mdnsflushcache
~~~

**OSX 10.9 - 10.8 – 10.7**

~~~
sudo killall -HUP mDNSResponder
~~~

**OSX 10.5 - 10.6**

~~~
sudo dscacheutil -flushcache
~~~

**Windows**

~~~
ipconfig /flushdns
~~~

**Linux (depending on what you’re running)**

~~~
/etc/init.d/named restart
~~~

or 

~~~
/etc/init.d/nscd restart
~~~

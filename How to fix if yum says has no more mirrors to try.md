Suppose you run `yum update` but Linux CentOS always says `has no more mirrors to try`. Just execute this.

~~~
sudo yum clean metadata
~~~

and try again your `yum update`

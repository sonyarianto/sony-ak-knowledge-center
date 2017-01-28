First, this is the scenario.

I have CentOS 7 with LEMP stack (Nginx and PHP 7.0 from IUS package)

I want to upgrade PHP from PHP 7.0 to PHP 7.1 (still from IUS package)

Here is the steps.

Check first your current PHP installation with command

```
rpm -qa | grep php
```

Install below.

```
yum install yum-plugin-replace
```

Because I am using PHP FPM then type below

```
yum replace php70u-fpm-nginx --replace-with php71u-fpm-nginx
```

Everything should be OK, but maybe you need to adjust file

```
/etc/php-fpm.d/www.conf
```
and
```
/etc/nginx/conf.d/php-fpm.conf
```

and usually php-fpm not start on boot, don't worry just type

```
systemctl enable php-fpm
```

Some reference:
* https://www.digitalocean.com/community/tutorials/how-to-upgrade-to-php-7-on-centos-7
* https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-centos-7
* https://community.rackspace.com/general/f/34/p/8055/13887

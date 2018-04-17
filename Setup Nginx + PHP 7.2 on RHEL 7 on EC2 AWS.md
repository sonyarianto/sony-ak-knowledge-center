I like combination of Nginx, PHP latest (currently 7.2) and a good hardware and OS (RHEL 7 on AWS EC2). Here is my setup experience on it.

1. Setup EC2 on AWS and use RHEL 7 as OS image. Choose `t2.micro` and 30 GB storage (I think this is still on free-tier area). Don't forget to setup proper Security Group (on mine just open port 80, 443 and 22 for starting). Setup proper key-pair and then try to logged-in to the server using `ec2-user` and your private key.
2. Do `sudo su` to become `root` and usually I type below.
   * `yum update`
   * `yum install wget`
3. Here your system ready to be installed with Nginx. Yes I choose Nginx for first install.
4. Go `http://nginx.org/en/linux_packages.html` and choose the Mainline version. No problem for production.
5. Type `vi /etc/yum.repos.d/nginx.repo` to create repo for Nginx and fill that file with this.
```
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/mainline/rhel/7/$basearch/
gpgcheck=0
enabled=1
```

Look above we use `rhel` and `7` on OS and version respectively.

6. Type `yum update` and then type `yum install nginx`
7. Start Nginx by typing `systemctl start nginx` and then set Nginx to start on boot by typing `systemctl enable nginx`. Check your Nginx version setup by typing `nginx -v`. It should display like below.
```
nginx version: nginx/1.13.12
```
8. Relax a bit and test your Nginx setup by accessing it from your web browser, pointing to your EC2 public IP address. If your setup OK then it will display the default Nginx web page.
9. Now get ready to install the PHP 7.2.
10. I prefer PHP from IUS package to install. I don't know why, just my habit :)
11. Go to `https://ius.io/GettingStarted/` and read on `Install via Automation` section.
12. I usually download the bash script from there section. Just type `wget https://setup.ius.io/` on your EC2 (as root). Usually it will download `index.html` then rename it by `mv index.html setup.sh` then set it executable by `chmod +x setup.sh`
13. Then run it by `./setup.sh` and let it flow.
14. Install PHP 7.2 (by this time is 7.2.3) by typing like below.
```
yum install php72u-cli php72u-common php72u-mysqlnd \
            php72u-pecl-memcached php72u-mbstring php72u-opcache \
            php72u-fpm php72u-fpm-nginx php72u-json php72u-pecl-igbinary \
            php72u-pdo php72u-xml php72u-process php72u-devel
```
15. Relax again and test your PHP setup by typing `php -v`. It should display something like below.
```
PHP 7.2.3 (cli) (built: Mar  1 2018 14:56:22) ( NTS )
Copyright (c) 1997-2018 The PHP Group
Zend Engine v3.2.0, Copyright (c) 1998-2018 Zend Technologies
    with Zend OPcache v7.2.3, Copyright (c) 1999-2018, by Zend Technologies
```
16. Now I will disable SELinux. To check if it enabled just type `getenforce` and if it display `Enforcing` it means it enabled.
17. Another to check is by typing `sestatus`. If it enabled will display similar like below.
```
SELinux status:                 enabled
```
18. To disable SELinux permanently just edit file `/etc/selinux/config` and change this line.
```
SELINUX=enforcing
```
to
```
SELINUX=disabled
```
19. Reboot your EC2 by typing `shutdown -r now`
20. Now connect your PHP 7.2 with Nginx, so your Nginx can serve your PHP file.
21. Open file `/etc/php-fpm.d/www.conf`
22. On my configuration user is like below.
```
user = php-fpm
group = php-fpm
```
23. Change the `listen` part like below.
```
listen = 127.0.0.1:9000
```
to
```
listen = /run/php-fpm/www.sock
```
24. Set the `listen.acl_users` part like below.
```
listen.acl_users = nginx
```
25. On `listen.owner` and `listen.group` and `listen.mode` on mine is on default like below.
```
;listen.owner = root
;listen.group = root
;listen.mode = 0660
```
26. I don't edit file `/etc/nginx/nginx.conf` and leave it like default.
27. On my folder `/etc/nginx` is like below.
```
total 36
drwxr-xr-x. 2 root root   75 Apr 16 11:04 conf.d
drwxr-xr-x. 2 root root   22 Apr 16 10:30 default.d
-rw-r--r--. 1 root root 1007 Apr 10 14:25 fastcgi_params
-rw-r--r--. 1 root root 2837 Apr 10 14:25 koi-utf
-rw-r--r--. 1 root root 2223 Apr 10 14:25 koi-win
-rw-r--r--. 1 root root 5170 Apr 10 14:25 mime.types
lrwxrwxrwx. 1 root root   29 Apr 16 10:21 modules -> ../../usr/lib64/nginx/modules
-rw-r--r--. 1 root root  643 Apr 10 14:23 nginx.conf
-rw-r--r--. 1 root root  636 Apr 10 14:25 scgi_params
-rw-r--r--. 1 root root  664 Apr 10 14:25 uwsgi_params
-rw-r--r--. 1 root root 3610 Apr 10 14:25 win-utf
```
28. I will create my virtualhost setup for my PHP + Nginx setup on folder `conf.d/`
29. I go to folder `conf.d/` and create new file called `my-virtual-host.conf` for later to be processed by Nginx.
30. Why Nginx can read my `my-virtual-host.conf` config? It because on `/etc/nginx/nginx.conf` there is line like below.
```
include /etc/nginx/conf.d/*.conf;
```
It will read all files that has extension `.conf` and later processed by Nginx.
31. Back again to our virtual host file `/etc/nginx/conf.d/my-virtual-host.conf`. I fill it like below.
```
server {
    listen 80;
    server_name  my-domain.id;

    root   /web/test/public;
    index index.php index.html index.htm;

    error_log  /var/log/nginx/my-domain.id.log  warn;

    location / {
      #try_files $uri $uri/ =404;
      try_files $uri /index.php$is_args$args;
    }

    location ~ \.php$ {
        try_files $uri =404;
        fastcgi_pass unix:/run/php-fpm/www.sock;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }
}
```
32. Save it before I explain it.
33. Part like `server_name` is for your domain to be setup.
34. Part like `root` is for your folder of your PHP project/web/framework etc.
35. Part like `error_log` is for your error log for this domain. This is important for later debuging.
36. Restart Nginx and PHP FPM by typing `systemctl restart nginx` then `systemctl restart php-fpm`
37. Create your test PHP script, my favorite is create this file `pi.php`
```
<?php phpinfo();
```
38. Run it from your browser (by typing http://my-domain.id/pi.php) and if everything OK then it will display the PHP info page.
39. That's all.


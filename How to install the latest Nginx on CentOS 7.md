If you follow Nginx installation tutorial in https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-centos-7 then you will get Nginx 1.6.3 installed. That's quite old. How to update to the latest one?

It's easy, you just add nginx repo.

1. Go to `/etc/yum.repos.d/`
2. Create file called `nginx.repo`
3. Go to https://www.nginx.com/resources/wiki/start/topics/tutorials/install/
4. If you use CentOS then copy the repo information there to your `nginx.repo` file.
```
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
gpgcheck=0
enabled=1
```
5. Save it and then run `yum clean all` and then run `yum update`
6. That's it boys!

CentOS release 6.7 (Final)

`yum update` fails on the error below.
```
http://mirror.centos.org/centos/6/SCL/x86_64/repodata/repomd.xml: [Errno 14] PYCURL ERROR 22 - "The requested URL returned error: 404 Not Found"
```

Here is the workaround
```bash
sudo yum remove centos-release-scl
sudo yum update # Update to CentOS 6.8
sudo yum install centos-release-scl
sudo yum update
```

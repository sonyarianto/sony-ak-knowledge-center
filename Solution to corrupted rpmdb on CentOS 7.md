I got this.

```
[root@server sony]# yum update
Failed to set locale, defaulting to C
rpmdb: Thread/process 4919/140273588029344 failed: Thread died in Berkeley DB library
error: db3 error(-30974) from dbenv->failchk: DB_RUNRECOVERY: Fatal error, run database recovery
error: cannot open Packages index using db3 -  (-30974)
error: cannot open Packages database in /var/lib/rpm
CRITICAL:yum.main:

Error: rpmdb open failed
[root@server sony]#
```

then do this

```
rm -f /var/lib/rpm/__*
rpm --rebuilddb
rpm -qa | wc -l
```

I have CentOS 7.5 running.
```
LSB Version:	:core-4.1-amd64:core-4.1-noarch:cxx-4.1-amd64:cxx-4.1-noarch:desktop-4.1-amd64:desktop-4.1-noarch:languages-4.1-amd64:languages-4.1-noarch:printing-4.1-amd64:printing-4.1-noarch
Distributor ID:	CentOS
Description:	CentOS Linux release 7.5.1804 (Core) 
Release:	7.5.1804
Codename:	Core
```

and I have MySQL 5.7.23 running. Also I have PHP 7.2 running.
```
PHP 7.2.8 (cli) (built: Jul 19 2018 11:58:32) ( NTS )
Copyright (c) 1997-2018 The PHP Group
Zend Engine v3.2.0, Copyright (c) 1998-2018 Zend Technologies
    with Zend OPcache v7.2.8, Copyright (c) 1999-2018, by Zend Technologies
```

Today I upgrade MySQL to 8.0.12 and run `mysql_upgrade` after upgrade.

Suddenly my PHP application cannot run. No problem! Here is the solution.

Open file `/etc/my.cnf` and add this into `[mysqld]` section.

```
# added by Sony AK
default_authentication_plugin=mysql_native_password
```

Then restart the MySQL by typing `systemctl restart mysqld` and after that refresh you PHP and it works man!

`MySQL` `v5.7` or higher generates a temporary random password after installation and stored that in mysql error log file, located at `/var/log/mysqld.log` for an installation by the `MySQL` `yum` repository on `CentOS 7`.

Use below command to see the password:
```
sudo grep 'temporary password' /var/log/mysqld.log
```

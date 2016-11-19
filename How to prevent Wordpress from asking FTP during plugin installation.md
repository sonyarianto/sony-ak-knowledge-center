I assume you have VPS that you can do anything on your server.

1. We will enable upgrade/install plugin by SSH2.
2. Go to your server and type `pecl install ssh2` (if you don't have pecl just install it first by typing `yum -y install php-pear`
3. If during install `ssh2` there is trouble than please install the libraries by type 'yum install libssh2-devel'
4. If you success then system will provide extension that you should add on your `php.ini` file.
5. Now to go your `wp-config.php` and add these:
```
define('FTP_USER', 'your_ssh_user');
define('FTP_PASS', 'your_ssh_password');
define('FTP_HOST', 'your_ssh_host_or_localhost');
define('FS_METHOD', 'ssh2'); // this is fix
```
That's it now go to your `Wordpress` admin and try to install any plugin.

Or you can set ownership on your Wordpress folder to web server user. Example like below.

1. Go to your WP folder from SSH
2. Just type `sudo chown -R apache:apache *`

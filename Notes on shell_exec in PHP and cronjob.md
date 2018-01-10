On PHP CLI you can do shell_exec with direct command. Such as this.

```php
shell_exec('vipsheader --field=width /my/image/folder/anything.jpg');
```

But on cronjob, above command will not work properly, since cronjob environment doesn't understand the PATH. Do this.

First get where exact path location of your app, above context is `whereis vipsheader`.

After that on `shell_exec` do like this.

```php
shell_exec('/usr/local/bin/vipsheader --field=width /my/image/folder/anything.jpg');
```

Or read this https://stackoverflow.com/questions/46934471/php-shell-execcmd-do-not-run-in-a-cronjob

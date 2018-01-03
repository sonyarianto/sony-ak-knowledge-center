```php
echo shell_exec('cd /my/repository/folder/repository-name && /usr/bin/git pull 2>&1');
```

The `2>&1` is to display STDERR.

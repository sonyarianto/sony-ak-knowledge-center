You typically should run `update` on your machine, then commit/deploy the `composer.lock` file and only run `install` on your server to sync up the dependencies with the lock file, to make sure you only get stuff you tested properly. That way you can also run a server with low memory without any problems.

Example:

1. Do `composer require xxx` or `php composer.phar require xxx` on your local machine
2. System will update the `composer.lock` file
3. Copy this `composer.lock` to your server (development or production)
4. Do `composer install` or `php composer.phar install' on your server with minimal RAM

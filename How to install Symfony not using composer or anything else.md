Suppose you want to install Symfony 2.3

* Download from `https://github.com/symfony/symfony-standard/tree/2.3` as zip and extract on your local
* Upload to server
* Make sure set permission full access for folder `logs` and `cache` on `app/` folder
* Download composer on Symfony folder with command `wget https://getcomposer.org/composer.phar`
* From Symfony folder run `php composer.phar install`
* Make sure your web server already point to Symfony `web` folder

That's it boys.

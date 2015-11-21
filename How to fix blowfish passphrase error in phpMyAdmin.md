Just open file `config.inc.php` on your `phpMyAdmin` folder. If not exists just copy it from the default `config.sample.inc.php` on that folder. Then edit this line and fill with your secret string.

~~~php
$cfg['blowfish_secret'] = ''; /* YOU MUST FILL IN THIS FOR COOKIE AUTH! */
~~~

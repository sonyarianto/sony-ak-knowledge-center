Just read here for the concept https://medium.com/php-7-tutorial/solution-how-to-compile-php7-with-ssh2-f23de4e9c319

For CentOS here what I do.

Get the source from https://github.com/Sean-Der/pecl-networking-ssh2/archive/php7.zip
```
wget https://github.com/Sean-Der/pecl-networking-ssh2/archive/php7.zip
```

Unzip using this.
```
unzip php7.zip
```
Go to the extracted directory, then run this.
```
phpize
```
Then do this.
```
make
```
Then do this.
```
make install
```
Then edit your `php.ini` and add `extension=ssh2.so`

Then restart your PHP.

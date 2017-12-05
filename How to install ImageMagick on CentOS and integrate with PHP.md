I write this because ImageMagick is very dynamic software in update release perspective and often is not updated if we use repository. So my advice is to build from source.

If your system already have imagick from remi repo then please remove it first.

Now we will show you to build imagick from source.

Download from latest source.
~~~bash
wget http://www.imagemagick.org/download/ImageMagick.tar.gz
~~~

Extract it.
~~~bash
tar xvzf ImageMagick.tar.gz
~~~

Go inside the folder and type these commands.
~~~bash
./configure
make
make install
ldconfig /usr/local/lib
~~~

Now install the PHP library using this command.
~~~bash
pecl install imagick
~~~

If imagick already installed then remove first with
```bash
pecl uninstall imagick
```

Add these line to php.ini.
~~~
extension=imagick.so
~~~

Now test the installed version by typing this.
~~~bash
convert --version
~~~

You are done!


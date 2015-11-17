Install the UglifyJS and UglifyCSS using `npm` locally.

Now starts with UglifyJS first. Go to your Symfony root folder and type below command.

~~~bash
cd /path/to/your/symfony/project
npm install uglify-js --prefix app/Resources
~~~

It will install UglifyJS locally on your `app/Resources/node_modules/.bin/uglifyjs`.

From here you can execute

~~~bash
./app/Resources/node_modules/.bin/uglifyjs --help
~~~

To test your installation of UglifyJS is success.

Now install UglifyCSS. Go to your Symfony root folder and type below command.

~~~bash
cd /path/to/your/symfony/project
npm install uglifycss --prefix app/Resources
~~~

It will install UglifyCSS locally on your `app/Resources/node_modules/.bin/uglifycss`.

Now open `config.yml` and edit like below.

~~~yml
# app/config/config.yml
assetic:
    # the path to the node executable and maybe different with your system
    node: /usr/bin/nodejs
    filters:
        uglifyjs2:
            # the path to the uglifyjs executable
            bin: bin: %kernel.root_dir%/Resources/node_modules/.bin/uglifyjs
        uglifycss:
            bin: %kernel.root_dir%/Resources/node_modules/.bin/uglifycss
            ugly_comments: true
~~~

Until now your Symfony already installed with UglifyJS and UglifyCSS and let's use it on your Twig like below.

~~~twig
{% javascripts '@AppBundle/Resources/public/js/*' filter='uglifyjs2' %}
    <script src="{{ asset_url }}"></script>
{% endjavascripts %}
~~~

and

~~~twig
{% stylesheets '@AppBundle/Resources/public/js/style.css' filter="uglifycss" %}
    <link rel="stylesheet" href="{{ asset_url }}"/>
{% endstylesheets %}
~~~

Now delete your Symfony `cache` and try to access the website and now your minification of JS and CSS should be success.

References:
- http://symfony.com/doc/current/cookbook/assetic/uglifyjs.html

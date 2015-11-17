Install the UglifyJS and UglifyCSS using `npm` locally.

Now starts with UglifyJS first.
Go to your Symfony root folder and type below command.

~~~
cd /path/to/your/symfony/project
npm install uglify-js --prefix app/Resources
~~~

It will install UglifyJS locally on your `app/Resources/node_modules/.bin/uglifyjs`.

From here you can execute

~~~
./app/Resources/node_modules/.bin/uglifyjs --help
~~~

To test your installation of UglifyJS is success.

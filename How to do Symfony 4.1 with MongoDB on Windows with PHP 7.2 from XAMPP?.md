I assume you are able to do these steps:

1. XAMPP with 7.2 installed.
2. Then you should enable or install the PHP extension for MongoDB. Since I am on Windows 10 machine then I download from this https://pecl.php.net/package/mongodb/1.5.2/windows and choose `7.2 Thread Safe (TS) x86` version of DLL.
3. Extract the zip and put the .dll file to your XAMPP\php\ext
4. Add the extension on php.ini (mine on c:\XAMPP\php\php.ini) like this `extension=php_mongodb.dll`
5. Verify with `php -i` and look on the status of mongodb extension
6. Install the latest Symfony from this documentation https://symfony.com/doc/current/setup.html
7. Install doctrine MongoDB here https://www.doctrine-project.org/projects/doctrine-mongodb-odm/en/latest/reference/introduction.html#using-php-7
8. My experience is run this from your fresh Symfony 4.1 installation `composer config "platform.ext-mongo" "1.6.16" && composer require "alcaeus/mongo-php-adapter"`
9. Make sure your MongoDB server run on your localhost
10. Go to Symfony .env and check the `MONGODB_URL` and `MONGODB_DB`
11. Create controller and do like below. Below is like DBAL in MySQL and I like it instead of using ODM/ORM hahaha.

```
$m = $this->container->get('doctrine_mongodb.odm.default_connection');

// select a database
$db = $m->selectDatabase('symfony');

// select a collection (analogous to a relational database's table)
$collection = $db->createCollection('cartoons');

// add a record
$document = array( "title" => "Calvin and Hobbes", "author" => "Bill Watterson" );
$collection->insert($document);

// find everything in the collection
$cursor = $collection->find();
```

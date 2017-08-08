Look at this code.

```php
$connectionFactory = $this->container->get('doctrine.dbal.connection_factory');
$connection = $connectionFactory->createConnection(array(
    'driver'    => 'pdo_mysql',
    'user'      => '',
    'password'  => '',
    'host'      => '',
    'dbname'    => '',
));
```

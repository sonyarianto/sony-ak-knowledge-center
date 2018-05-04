On `app/config.yml`

```
imports:
    - { resource: parameters.php }
    
# Doctrine Configuration
doctrine:
    dbal:
        default_connection: default
        connections:
            default:
                driver:   %database_driver%
                host:     %database_host%
                port:     %database_port%
                dbname:   %database_name%
                user:     %database_user%
                password: %database_password%
                charset:  UTF8
            second_db:
                driver:   %2nd_database_driver%
                host:     %2nd_database_host%
                port:     %2nd_database_port%
                dbname:   %2nd_database_name%
                user:     %2nd_database_user%
                password: %2nd_database_password%
                charset:  UTF8

    orm:
        default_entity_manager: default
        entity_managers:
            default:
                connection: default
            second_db:
                connection: second_db

parameters:
    2nd_database_driver:   pdo_mysql
    2nd_database_port:     ~
```

On `parameters.php`
```
<?php
	$container->setParameter('2nd_database_host', getenv('2ND_DATABASE_HOST'));
	$container->setParameter('2nd_database_name', getenv('2ND_DATABASE_NAME'));
	$container->setParameter('2nd_database_user', getenv('2ND_DATABASE_USER'));
	$container->setParameter('2nd_database_password', getenv('2ND_DATABASE_PASSWORD'));
```

On controller.

```
use Doctrine\DBAL\Connection;
```

```
public function indexAction()
{ 	
  $conn = $this->get('doctrine')->getManager('second_db')->getConnection();

  $users = $conn->fetchAll('SELECT * FROM users');
  var_dump($users);
  echo "--------------";
  echo getenv('2ND_DATABASE_HOST');
  exit;
  
  //return $this->render('XBundle:X:index.html.twig');
}
```

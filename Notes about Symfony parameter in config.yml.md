Suppose you want to store data on config.yml and you want that's accessible from controller.

On `config.yml` suppose like this.

```
parameters:
  my_data:
    data1:
      - {'element1': 'element1_value', 'element2': 'element2_value'}
      - {'element1': 'element11_value', 'element2': 'element22_value'}
    data2:
      - {'element11': 'element11_value', 'element22': 'element22_value'}
      - {'element11': 'element111_value', 'element22': 'element222_value'}
```

On controller you can call like this.

```php
  $my_data = $container->getParameter('my_data');
```

or 

```php
  $my_data = $this->container->getParameter('my_data');
```

If we `var_dump($my_data)` it will be like below.

```php
array(2) {
  ["data1"]=>
  array(2) {
    [0]=>
    array(2) {
      ["element1"]=>
      string(14) "element1_value"
      ["element2"]=>
      string(14) "element2_value"
    }
    [1]=>
    array(2) {
      ["element1"]=>
      string(15) "element11_value"
      ["element2"]=>
      string(15) "element22_value"
    }
  }
  ["data2"]=>
  array(2) {
    [0]=>
    array(2) {
      ["element11"]=>
      string(15) "element11_value"
      ["element22"]=>
      string(15) "element22_value"
    }
    [1]=>
    array(2) {
      ["element11"]=>
      string(16) "element111_value"
      ["element22"]=>
      string(16) "element222_value"
    }
  }
}
```

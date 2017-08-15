Suppose you have array like this.

```
$my_array = array(
              array('name' => 'Car', 'price' => 12),
              array('name' => 'House', 'price' => 500),
              array('name' => 'Banana', 'price' => 2)
              )
```

```
array_multisort(array_column($my_array, 'price'), SORT_ASC, $my_array);
```

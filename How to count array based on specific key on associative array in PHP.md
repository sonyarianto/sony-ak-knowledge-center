Imagine this array structure.

~~~php
array(0 => array('category_id' => 10),
      1 => array('category_id' => 20,
      2 => array('category_id' => 10));
~~~

You want to create facet of each category_id then use this code.

~~~php
array_count_values(array_map(function($foo){return $foo['category_id'];}, $stationsWithCategory)));
~~~

It will return

~~~
Array ( [10] => 2 [20] => 1 ) 
~~~

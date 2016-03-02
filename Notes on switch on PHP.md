Look at this `PHP` code.
~~~
switch(true){
 case 1 == 2:
   echo '1 == 2';
   break;
 case 2 == 2:
   echo '2 == 2';
   break;
 case 3 == 3:
   echo '3 == 3';
   break;
 case 4 == 1:
   echo '4 == 1';
   break;
}
~~~
It will output `2 == 2` since `switch(true)` will only return the first `true` condition.

Suppose you want to convert GMT datetime to Jakarta (GMT+7) time.

~~~php
<?php
    $date = new DateTime('2015-06-17T06:04:22Z', new DateTimeZone('+00:00'));
    echo $date->format('Y-m-d H:i:s') . "\n";

    $date->setTimezone(new DateTimeZone('+07:00'));
    echo $date->format('Y-m-d H:i:s') . "\n";
~~~

Another example by using timezone area string.

~~~php
<?php
    $date = new DateTime('2015-06-17T06:04:22Z', new DateTimeZone('GMT'));
    echo $date->format('Y-m-d H:i:s') . "\n";

    $date->setTimezone(new DateTimeZone('Asia/Jakarta'));
    echo $date->format('Y-m-d H:i:s') . "\n";
~~~

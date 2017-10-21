See below and you will be understand.
```php
<?php

function inverse($x) {
    if (!$x) {
        throw new Exception('Division by zero.');
    }
    return 1/$x;
}

try {
    echo "This will be executed first!\n";
    echo inverse(0) . "\n";
    echo "This will not executed!\n";
} catch (Exception $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
} finally {
    echo "This will always executed!\n";
}

// Continue execution
echo "This is the last will be executed!\n";
```

Here is the output.
```
This will be executed first!
Caught exception: Division by zero.
This will always executed!
This is the last will be executed!
```

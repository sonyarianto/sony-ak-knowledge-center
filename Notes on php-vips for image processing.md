Sample:
```php
<?php

require __DIR__ . '/vendor/autoload.php';

use Jcupitt\Vips;

$buffer = file_get_contents($uri);
$image = Vips\Image::newFromBuffer($buffer, ['page' => 12, 'dpi' => 144]);
$pngfile = $image->writeToBuffer('.png');
```

and also read this https://github.com/jcupitt/php-vips

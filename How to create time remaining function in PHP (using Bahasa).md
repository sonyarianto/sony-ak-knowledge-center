```php
  function timeRemaining($target_datetime) {
		$today = new DateTime(null, new DateTimeZone('Asia/Jakarta'));
		$target  = new DateTime($target_datetime, new DateTimeZone('Asia/Jakarta'));

		$timeRemaining 			= $target->diff($today)->m . " bln " . $target->diff($today)->days . " hari " . $target->diff($today)->h . " jam " . $target->diff($today)->i . " mnt lagi"; 
		$timeRemaining			= str_replace(["0 bln ", " 0 hari ", " 0 jam ", " 0 mnt"], " ", $timeRemaining);

		if($target->diff($today)->days > 0) {
			$timeRemaining 		= $target->diff($today)->days . " hari lagi";
		}

		if($target->diff($today)->m > 0) {
			$timeRemaining 		= $target->diff($today)->m . " bulan lagi";
		}

		return $timeRemaining; 
	}
```

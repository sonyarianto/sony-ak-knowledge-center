Notes: variable `$happening_time` is Unix time format (e.g. `UNIX_TIMESTAMP` in `MySQL`)

```php
    function timeAgo($happening_time) {
    	$timeDifference = time() - $happening_time;

    	$seconds    	= $timeDifference;
    	if($seconds <= 60) { return "$seconds dtk lalu"; }

    	$minutes    = round($timeDifference / 60);
    	if($minutes <= 60) {
			  if($minutes == 1) { return "satu mnt lalu"; } else {return "$minutes mnt lalu"; }
    	}
   
    	$hours      = round($timeDifference / 3600);
    	if($hours <= 24) {
			  if($hours == 1) { return "satu jam lalu"; } else { return "$hours jam lalu"; }
    	}
   
    	$days      = round($timeDifference / 86400);
		  if($days <= 7) {
			  if($days == 1) { return "satu hari lalu"; } else { return "$days hari lalu"; }
    	}
   
    	$weeks      = round($timeDifference / 604800);
    	if($weeks <= 4) {
			  if($weeks == 1) { return "satu mgu lalu"; } else { return "$weeks mgu lalu"; }
    	}
   
    	$months    = round($timeDifference / 2419200);
    	if($months <= 12) {
			  if($months == 1) { return "satu bln lalu"; } else { return "$months bln lalu"; }
    	}
   
    	$years      = round($timeDifference / 29030400 );
    	if($years == 1) { return "satu thn lalu"; } else { return "$years thn lalu"; }
	}
```

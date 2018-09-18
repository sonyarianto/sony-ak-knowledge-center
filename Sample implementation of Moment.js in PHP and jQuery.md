```html
<?php
	//date_default_timezone_set('Asia/Jakarta');
	date_default_timezone_set('GMT');

	//$predefinedDatetime = 1534442400; // GMT UNIX Timestamp
	$predefinedDatetime = strtotime(date('Y-m-d H:i:s')); // GMT UNIX Timestamp

?>
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">

    <title>Moment.js</title>
  </head>
  <body>
    <div>Waktu saat ini <span data-timestamp="<?php echo $predefinedDatetime; ?>"><?php echo date("Y-m-d H:i:s", $predefinedDatetime); ?></span></div>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <!-- <script src="/moment.min.js"></script> -->
    <script src="/moment-with-locales.min.js"></script>
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js" integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js" integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy" crossorigin="anonymous"></script>
  
  	<script>
  		$( document ).ready(function() {
    		$("[data-timestamp]").each(function() {
			    var el = $(this);
			    var timeValue = el.attr("data-timestamp");
			    var localTime = moment.unix(timeValue).format('YYYY-MM-DD HH:mm:ss');
			    //var localTime = moment.unix(timeValue).fromNow();
			    el.text(localTime);
			    // switch(el.attr("data-timestamp")) {
			    //     case "time-ago":
			    //     var timeValue = el.attr("data-time-value")
			    //     var strTimeAgo = moment.unix(timeValue).fromNow();
			    //     el.text(strTimeAgo);
			    //     break;
			    // }
			});
		});
  	</script>
  </body>
</html>
```

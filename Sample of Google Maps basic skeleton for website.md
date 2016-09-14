```javascript
<script src="https://maps.googleapis.com/maps/api/js?key=API_KEY&callback=initMap" async defer></script>
<script type="text/javascript">
	var map;
	var marker;
	function initMap() {
		map = new google.maps.Map(document.getElementById('map-container'), {
	    	center: {lat: -6.205837, lng: 106.839118}, // set to Jakarta
	      	zoom: 14,
	        mapTypeControl: true,
	        mapTypeControlOptions: {
	        	style: google.maps.MapTypeControlStyle.HORIZONTAL_BAR,
				position: google.maps.ControlPosition.TOP_RIGHT
			}
		});
		var myLatlng = new google.maps.LatLng(-6.199148, 106.833152); // set to Taman Suropati
		marker = new google.maps.Marker({
		    position: myLatlng,
		    title:"Hello World!"
		});

		// To add the marker to the map, call setMap();
		marker.setMap(map);

		map.panTo(marker.getPosition());
	}

	$(".detail-map-container .map-container .map-container-option a.centered-option").click(function() {
		map.panTo(marker.getPosition());
	});
</script>
```

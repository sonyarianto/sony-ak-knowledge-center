I have question in Stackovrflow and here is great answer.

I have code like below.

~~~html
<!DOCTYPE html>
<html>
  <head>
    <style type="text/css">
      html, body { height: 100%; margin: 0; padding: 0; }
      #map { height: 100%; }
    </style>
  </head>
  <body>
    <input type="hidden" id="zoom_data" value="8">
    <div id="map"></div>
    <script type="text/javascript">

var map;
function initMap() {
  map = new google.maps.Map(document.getElementById('map'), {
    center: {lat: -34.397, lng: 150.644},
    zoom: $('#zoom_data').val()
  });
}

    </script>
    <script async defer
      src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap">
    </script>
  </body>
</html>
~~~

But the maps goes blank. I just want to dynamically set zoom locally, not from server. Any advice?

Now here is the answer.

Try the code below. You need to use document.getElementById() to get the value of the hidden field then convert it to number before using it as a zoom parameter.

~~~html
<!DOCTYPE html>
<html>
  <head>
    <style type="text/css">
      html, body { height: 100%; margin: 0; padding: 0; }
      #map { height: 100%; }
    </style>
  </head>
  <body>
    <input type="hidden" id="zoom_data" value="8">
    <div id="map"></div>
    <script type="text/javascript">

var map;
 function initMap() {
    var zoom = document.getElementById('zoom_data').value;
    var nZoom = Number(zoom);
     map = new google.maps.Map(document.getElementById('map'), {
    center: {lat: -34.397, lng: 150.644},
    zoom: nZoom
  });
}

</script>
<script async defer
  src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap">
</script>
~~~

Hope it helps! Answer from http://stackoverflow.com/users/5637474/grenzfries


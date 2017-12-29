```js
const cloudscraper = require('cloudscraper');

cloudscraper.get('http://www.sundul.com/feed/', function(error, response, body) {
  if (error) {
    console.log('Error occurred');
  } else {
    //console.log(body, response);
    console.log(body);
  }
});
```

```javascript
var page = require('webpage').create();
page.open('http://www.google.com', function(status) {
  console.log("Status: " + status);
  if(status === "success") {
    console.log(page.content) // print source to console
  }
  phantom.exit();
});
```

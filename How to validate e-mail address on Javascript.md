I am using this for now. I assume we have `input` element with `id="email_address"`

```javascript
var jet = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
if(jet.test($('#email_address').val()) == false) {
  alert('email address not valid');
}
```

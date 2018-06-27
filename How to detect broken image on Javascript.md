```javascript
document.addEventListener(“DOMContentLoaded”, function(event) {
  document.querySelectorAll(‘img’).forEach(function(img){
    img.onerror = function(){
      this.src = 'img/share/default.png';
    };
  })
});
```

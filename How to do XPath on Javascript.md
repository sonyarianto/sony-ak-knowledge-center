```js
var iterator = document.evaluate('(//div[contains(@class, "area-list")])[1]/div[@class="row"]//a', document, null, XPathResult.UNORDERED_NODE_ITERATOR_TYPE, null );

try {
  var thisNode = iterator.iterateNext();
  
  while (thisNode) {
    console.log(thisNode.textContent.trim());
    thisNode = iterator.iterateNext();
  }	
}
catch (e) {
  alert( 'Error: Document tree modified during iteration ' + e );
}
```

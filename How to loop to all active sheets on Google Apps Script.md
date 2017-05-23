This sample is loop to all sheets and clear sheets content that sheet name is not 'Source'.

```js
var ss = SpreadsheetApp.getActive();
var allsheets = ss.getSheets();  
for (var s in allsheets) {
  var sheet=allsheets[s];
  
  if (sheet.getSheetName() != 'Source') {
    sheet.clear();
  }
}
```

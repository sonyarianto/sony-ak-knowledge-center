```js
const chromeLauncher  = require('chrome-launcher');
const CDP             = require('chrome-remote-interface');
const fs              = require('fs');
const mysql           = require('mysql');
const appDate         = require('date-and-time');
const xmlserializer   = require('xmlserializer');

function launchChrome(headless=true) {
  return chromeLauncher.launch({
    // port: 9222, // use default port
    chromePath: '/usr/bin/google-chrome',
    chromeFlags: [
      //'--window-size=412,732', // set window size
      '--disable-gpu', // disable GPU
      '--no-sandbox', // no-sandbox
      '--proxy-server=206.196.111.197:80',
      '--headless' // do headless browsing
    ]
  });
}

// var dbConn = mysql.createConnection({
//   host     : '127.0.0.1',
//   user     : 'root',
//   password : 'Sakurniawan2001',
//   database : 'bolabanget_db'
// });

(async function() {
  const chrome    = await launchChrome();
  const protocol  = await CDP({port: chrome.port});

  // Extract the DevTools protocol domains we need and enable them.
  // See API docs: https://chromedevtools.github.io/devtools-protocol/
  const {Page, Runtime} = protocol;
  await Promise.all([Page.enable(), Runtime.enable()]);

  //Page.navigate({url: 'http://pojoksatu.id/bola/feed/'});
  Page.navigate({url: 'http://bolabanget.id'});
  // Page.navigate({url: 'http://www.yahoo.com'});

  // Wait for window.onload before doing stuff.
  Page.loadEventFired(async () => {
    //const js = "document.querySelector('title').textContent";
    //const js = "document.querySelector('html').outerHTML";
    const selectorOuterHtml = "document.documentElement.outerHTML";
    const selectorDoctype = "document.doctype";
  
    // Evaluate the JS expression in the page.
    const outerHtml = await Runtime.evaluate({expression: selectorOuterHtml});
    const docDoctype = await Runtime.evaluate({expression: selectorDoctype});

    if(!docDoctype.result.description) {
      var doctype = '';
    } else {
      var doctype = docDoctype.result.description;
    }

    console.log(docDoctype.result);
    //console.log(node);
    //console.log(outerHtml.result.value);
  
    /*
    fs.writeFile('ligaindonesia.id.html', result.result.value, (err) => {
      if (err) throw err;
    });
    */

    // dbConn.connect(function(err) {
    //   if(err) throw err;
    //   var sql = "UPDATE bb_stories_raw SET raw_data = ?, update_datetime = ? WHERE source_id = ?";
    //   dbConn.query(sql, [result.result.value, appDate.format(new Date(), 'YYYY-MM-DD HH:mm:ss'), 93], function (err, result) {
    //     if (err) throw err;
    //     console.log(result.affectedRows + " record(s) updated");
    //     console.log('Script Status: COMPLETE RUN');
    //     dbConn.end();
    //   });
    // });

    protocol.close();
    chrome.kill();
  });
})();
```

```js
const puppeteer = require('puppeteer');
const devices = require('puppeteer/DeviceDescriptors');
const iPhone = devices['iPhone 6'];

(async() => {
  const browser = await puppeteer.launch();
  let page = await browser.newPage();
  await page.emulate(iPhone);
  await page.goto('https://www.nytimes.com/');
  await page.screenshot({path: 'full.png', fullPage: true});
  browser.close();
})();
```

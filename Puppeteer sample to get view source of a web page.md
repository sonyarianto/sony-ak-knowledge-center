```js
const puppeteer = require('puppeteer');

(async () => {
  let puppeteer_params = { headless: true, args: ['--start-maximized', '--no-sandbox', '--disable-setuid-sandbox', '--single-process'] };

  if(process.platform == 'win32') {
    puppeteer_params = { headless: true };
  }

  const browser = await puppeteer.launch(puppeteer_params);
  const page = await browser.newPage();

  process.on("unhandledRejection", async (reason, p) => {
    console.error("Unhandled Rejection at: Promise", p, "reason:", reason);
    await browser.close();
    return;
  });

  await page.setUserAgent('Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/63.0.3239.132 Safari/537.36');
  await page.setExtraHTTPHeaders({
    'Accept-Language': 'en-GB,en-US;q=0.9,en;q=0.8'
  });

  try {
    const webPageSource = await page.goto('http://bolabanget.id');
    console.log(await webPageSource.text());
  } catch (error) {
    console.log(error);
    await browser.close();
    return;
  }

  await browser.close();
})();
```

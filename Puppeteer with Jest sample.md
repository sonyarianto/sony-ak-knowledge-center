```js
const puppeteer = require('puppeteer');

describe('LIFULL Produk Functional Test Suites', () => {
  var browser, page;

  beforeEach (async () => {
    window.jasmine.DEFAULT_TIMEOUT_INTERVAL = 60000;
    browser = await puppeteer.launch({ headless: true });
    page = await browser.newPage();
    await page.setViewport({width: 1600, height: 758});
  })

  afterEach (() => {
    browser.close()
  })

  test('Check Home Title = Dapatkan Sampel Produk Makanan dan Kecantikan Gratis｜LIFULL Produk', async () => {
    await page.goto('https://www.lifull-produk.id', {waitUntil: 'networkidle2'});
    const title = await page.title();

    expect(title).toBe("Dapatkan Sampel Produk Makanan dan Kecantikan Gratis｜LIFULL Produk");
  });

  test("Check login using existing user - non facebook - user: xxx@gmail.com", async () => {
    await page.goto('https://www.lifull-produk.id/login', {waitUntil: 'networkidle2'});
    await page.click('input[id=inputEmail]');
    await page.type('input[id=inputEmail]', 'xxx@gmail.com');
    await page.click('input[id=inputPassword]');
    await page.type('input[id=inputPassword]', 'xxx');
    await page.click('form[class=form-signin] > button[type=submit]');
    await page.waitForNavigation();
    const profile_picture_url = await page.$eval('img.img-circle.nav-ava.center-block', e => e.src);
    
    expect(profile_picture_url).toContain("/bundles/lifullproduk/img/profile-picture/6499520171107020413.png");
  });

  test("Check search keyword 'kiyora' on home page and result should exists", async () => {
    await page.goto('https://www.lifull-produk.id', {waitUntil: 'networkidle2'});
    await page.click('form[class=navbar-form] input[name=name]');
    await page.type('form[class=navbar-form] input[name=name]', 'kiyora');
    await page.click('form[class=navbar-form] button[type=submit]');
    await page.waitForNavigation();
    const product_exists_string = await page.$eval('div.left-content > p', e => e.innerHTML);
    
    expect(product_exists_string).toContain("hasil ditemukan.");
  });

  // test("Check forgot password send e-mail - non facebook - user: xxx@gmail.com", async () => {
  //   await page.goto('https://www.lifull-produk.id/forgot', {waitUntil: 'networkidle2'});
  //   await page.click('input[id=form_email]');
  //   await page.type('input[id=form_email]', 'xxx@gmail.com');
  //   await page.click('button[id=form_save]');
  //   await page.waitForNavigation();
  //   const alert_success = await page.$eval('div.alert.alert-danger', e => e.innerHTML);
    
  //   expect(alert_success).toContain("Link untuk me-reset password telah dikirim ke email Anda.");
  // });
})
```

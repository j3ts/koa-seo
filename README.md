[![Npm Package](https://img.shields.io/npm/v/koa-seo.svg?style=flat-square)](https://www.npmjs.com/package/koa-seo)
[![Npm Downloads](http://img.shields.io/npm/dm/koa-seo.svg?style=flat-square)](https://www.npmjs.com/package/koa-seo)
[![Dependency Status](https://david-dm.org/gwuhaolin/koa-seo.svg?style=flat-square)](https://npmjs.org/package/koa-seo)

# koa-seo
SEO middleware for koa base on [chrome-render](https://github.com/gwuhaolin/chrome-render), a substitute for [prerender](https://prerender.io).

Modern web app use technique like react.js vue.js which render html in browser, this lead to search engine can't crawl your page content.

This project want to solve this kind of problem in a general-purpose way, it detect request is from search engine crawler then use headless chrome to render out your modern web page and return to crawler.

## Use
```bash
npm i koa-seo
```
then use it:
```js
const Koa = require('koa');
const seoMiddleware = require('koa-seo');
const app = new Koa();

app.use(seoMiddleware({
    render: {
        // chrome-render #render() method ready option
        ready: '_page_ready',
    }
}));

app.listen(3000);
```
you can download and run this [complete demo](./demo/main.js)

## Options
- `render` options from [koa-chrome-render](https://github.com/gwuhaolin/koa-chrome-render#render-options)

For more flexible use case see [koa-chrome-render](https://github.com/gwuhaolin/koa-chrome-render).


## Friends
- [koa-chrome-render](https://github.com/gwuhaolin/koa-chrome-render) chrome-render middleware for koa.
- [chrome-render](https://github.com/gwuhaolin/chrome-render) general server render base on chrome.
- [chrome-pool](https://github.com/gwuhaolin/chrome-pool) Headless chrome tabs manage pool.

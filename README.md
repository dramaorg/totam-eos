# @dramaorg/totam-eos

Async and new alternative for the [g-i-s](https://www.npmjs.com/package/g-i-s).

## Installation
[![NPM](https://nodei.co/npm/@dramaorg/totam-eos.png?mini=true)](https://npmjs.org/package/@dramaorg/totam-eos)

## Note for old Node.js versions (below 18):
This package works with `fetch` api, if you use it on older versions of Node.js, you need to install `node-fetch` package defined in package.json.

## Usage

### Async/await Usage
```js
const gis = require('@dramaorg/totam-eos');

(async () => {
  try {

    const results = await gis("akif");
    console.log(results.slice(0, 10));

  } catch (e) {
    console.error(e);
  }
})();
```
### Promise Usage
```js
const gis = require('@dramaorg/totam-eos');

gis("akif").then(console.log).catch(console.error);
```


### Output:
```js
[
  {
    url: 'https://m.media-amazon.com/images/M/MV5BMWQwM2M4NDMtOTI3Ni00NTMyLWI4YzktYTNkMjcyYmYzNzY4XkEyXkFqcGdeQXVyMTMyMTYxODIy._V1_.jpg',
    height: 1477,
    width: 1034
  },
  {
    url: 'https://upload.wikimedia.org/wikipedia/tr/c/ca/AkifDizi.jpg',
    height: 350,
    width: 350
  },
  {
    url: 'https://upload.wikimedia.org/wikipedia/commons/7/7b/Mehmet_%C3%82kif_Ersoy.png',
    height: 1908,
    width: 1656
  },
  {
    url: 'https://erdemyayinlari.com.tr/wp-content/uploads/2021/12/akif.png',
    height: 450,
    width: 300
  },
  {
    url: 'https://cdnuploads.aa.com.tr/uploads/Contents/2021/12/26/thumbs_b_c_8d154765bbfa0e823854bff84badecad.jpg?v\\u003d132249',      
    height: 486,
    width: 864
  },
  {
    url: 'https://img.kitapyurdu.com/v1/getImage/fn:11653825/wh:true/wi:500',
    height: 779,
    width: 500
  },
  {
    url: 'https://img.a.transfermarkt.technology/portrait/big/526642-1629104912.jpg?lm\\u003d1',
    height: 390,
    width: 300
  },
  {
    url: 'https://i.ytimg.com/vi/Ycm31r2SaPo/maxresdefault.jpg',
    height: 720,
    width: 1280
  }
]
```
## Default Options 
```js
gis("", {
  query: {},
  userAgent: 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36'
});
```

- **User agent**: it is default user agent of Chrome. You can change it to anything you want.
- **Query**: You can add additional queries to URL. For example, you can add `safe: "on"` to filter out NSFW results.

```js
gis("akif", {
  query: { safe: "on" },
  userAgent: 'Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)'
});
```
Example, this will not fetch NSFW results. And change user agent to Googlebot.
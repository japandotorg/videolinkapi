# VIDEOLINKAPI

This module is used to fetch the video download url from a website.

Supports = YouTube, Instagram, Twitter, Kuaishou and Douyin for now, if you want me to add more stuff please create an issue [here](https://github.com/japandotorg/videolinkapi/issues).

## Installation

Make sure you have [Node.js](https://nodejs.org/en/) installed. Node.js 8.0 or higher is required.

```bash
$ npm install videolinkapi
```

## Usage

```js
const videoUrlLink = require('video-url-link');
```

### Get YouTube Info

```js
videoUrlLink.youtube.getInfo(url, [options], callback(error, info))
```

Example:
```js
videoUrlLink.youtube.getInfo('https://youtu.be/{ID}', { hl: 'en' }, (error, info) => {
    if (error) {
        console.error(error);
    } else {
        console.log(info.details);
        console.log(info.formats);
    }
});
```

### Get Instagram Info

```js
videoUrlLink.instagram.getInfo(url, [options], callback(error, info))
```

Example:
```js
videoUrlLink.instagram.getInfo('https://www.instagram.com/p/{ID}', (error, info) => {
    if (error) {
        console.error(error);
    } else {
        console.log(info.list);
    }
});
```

### Get Twitter Info

```js
videoUrlLink.twitter.getInfo(url, [options], callback(error, info))
```

Example:
```js
videoUrlLink.twitter.getInfo('https://twitter.com/{@}/status/{ID}', {}, (error, info) => {
    if (error) {
        console.error(error);
    } else {
        console.log(info.full_text);
        console.log(info.variants);
    }
});
```

### Get Douyin Info

```js
videoUrlLink.douyin.getInfo(url, [options], callback(error, info))
```

Example:
```js
videoUrlLink.douyin.getInfo('http://v.douyin.com/{ID}', (error, info) => {
    if (error) {
        console.error(error);
    } else {
        console.log(info.title);
        console.log(info.url);
    }
});
```

### Get Kuaishou Info

```js
videoUrlLink.kuaishou.getInfo(url, [options], callback(error, info))
```

Example:
```js
videoUrlLink.kuaishou.getInfo('http://www.gifshow.com/s/{ID}', (error, info) => {
    if (error) {
        console.error(error);
    } else {
        console.log(info.title);
        console.log(info.url);
    }
});
```

## Supported Sites

| Site | URL | Video? | Details? |
| :--- | :--- | :--- | :--- |
| YouTube | <https://www.youtube.com/>  | ✓ | ✓ |
| 抖音 | <https://www.douyin.com/>  | ✓ | ✓ |
| 快手 | <https://www.kuaishou.com/>  | ✓ | ✓ |
| Instagram | <https://www.instagram.com/>  | ✓ | ✓ |
| Twitter | <https://twitter.com>  | ✓ | ✓ |

## Testing

Testing has been done with [mocha](https://mochajs.org)

```bash
npm test
```
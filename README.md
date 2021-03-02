# bing-translate-api
[![NPM version](https://img.shields.io/npm/v/bing-translate-api.svg?style=flat)](https://www.npmjs.org/package/bing-translate-api)
[![Build Status](https://travis-ci.org/plainheart/bing-translate-api.svg?branch=master)](https://travis-ci.org/plainheart/bing-translate-api)
[![NPM Downloads](https://img.shields.io/npm/dm/bing-translate-api.svg)](https://npmcharts.com/compare/bing-translate-api?minimal=true)
[![License](https://img.shields.io/npm/l/bing-translate-api.svg)](https://www.npmjs.com/package/bing-translate-api)

A **simple** and **free** API for [Bing Translator](https://bing.com/translator) for Node.js.

## Install 

```
npm install bing-translate-api
```

## Usage

From auto-detected language to English:

```js
const { translate } = require('bing-translate-api');

translate('你好', null, 'en').then(res => {
  console.log(res.translation);
}).catch(err => {
  console.error(err);
});
```

Translation result

```json
{
  "text": "你好",
  "userLang": "auto-detect",
  "translation": "Hello",
  "language": {
    "to": "en",
    "from": "zh-Hans"
  }
}
```

## API

### translate(text, [from], [to], [raw], [tld], [userAgent])

#### text

Type: `string`

The text to be translated, cann't be blank.

##### from
Type: `string` Default: `auto-detect`

The language code of source text.
**MUST** be `auto-detect` or one of the codes/names (not case sensitive) contained in [lang.js](https://github.com/plainheart/bing-translate-api/blob/master/src/lang.js)

##### to
Type: `string` Default: `en`

The language in which the text should be translated.
**MUST** be one of the codes/names (not case sensitive) contained in [lang.js](https://github.com/plainheart/bing-translate-api/blob/master/src/lang.js).

##### raw
Type: `boolean` Default: `false`

Whether the translation result contains raw response from Bing API.

##### tld
Type: `string` Default: `''`

Can be `'www'` | `'cn'` | `''`

##### userAgent
Type: `string`

The header value of `user-agent` used in API requests. 

Default:
```
Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/88.0.4324.190 Safari/537.36
```

## License

MIT &copy; 2021 [plainheart](https://github.com/plainheart).

## Thanks

Great thanks to [Bing Translator](https://bing.com/translator) for providing so excellent translation service.

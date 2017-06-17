# audio-decode [![Build Status](https://travis-ci.org/audiojs/audio-decode.svg?branch=master)](https://travis-ci.org/audiojs/audio-decode) [![unstable](https://img.shields.io/badge/stability-unstable-green.svg)](http://github.com/badges/stability-badges) [![Greenkeeper badge](https://badges.greenkeeper.io/audiojs/audio-decode.svg)](https://greenkeeper.io/)

Convert encoded audio data in any format to [AudioBuffer](https://github.com/audiojs/audio-buffer). Basically [context.decodeAudioData](https://developer.mozilla.org/en-US/docs/Web/API/AudioContext/decodeAudioData) for node and browser.

[![npm install audio-decode](https://nodei.co/npm/audio-decode.png?mini=true)](https://npmjs.org/package/audio-decode/)

```js
const decode = require('audio-decode');
const buffer = require('audio-lena');
const getContext = require('audio-context');

//as a callback
decode(buffer, {context: getContext()}, (err, audioBuffer) => {});

//as a promise
decode(buffer, {context: getContext()}).then(audioBuffer => {}, err => {});
```

## API

**`let promise = decode(source, options?, callback?)`**

Decode `source`, based on `options` and fire `callback` when done, or resolve a promise if no callback passed. Source type can be: _ArrayBuffer_, _ArrayBufferView_, _Buffer_, _Blob_, _File_ or data-uri string.

Possible options may include `context` property for web-audio-api context. If not defined, the [audio-context](https://npmjs.org/package/audio-context) is used.

## Supported formats

Shipped by default:

* [x] _wav_ via [wav-decoder](https://github.com/mohayonao/wav-decoder)
* [x] _mp3_ via [aurora mp3](https://github.com/audiocogs/mp3.js)

To enable additional format, install it as a dependency `npm install --save flac.js` and require once `require('flac.js')`.

Additional formats available:

* [x] _flac_ via [flac.js](https://github.com/audiocogs/flac.js)
* [x] _alac_ via [alac.js](https://github.com/audiocogs/alac.js)
* [x] _aac_ via [aac.js](https://github.com/audiocogs/aac.js)


## Credits

* [@mohayonao](https://github.com/mohayonao/) for [wav-decoder](https://github.com/mohayonao/wav-decoder).
* [@devongovett](https://github.com/devongovett) and [@jensnockert](https://github.com/jensnockert) for [aurora.js](https://github.com/audiocogs/aurora.js).
* [@jamen](https://github.com/jamen) as originator of this package.


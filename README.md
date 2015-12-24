Formatted TAP output like Mocha's spec reporter

![screenshot](https://cloud.githubusercontent.com/assets/7221494/11996871/285614fc-aa2a-11e5-9d0d-9941d625ed0d.png)

## Install
This fork:
```
npm install --save-dev git+https://github.com/damionjn/tap-spec.git
```

Original [tap-spec](https://github.com/scottcorgan/tap-spec):
```
npm install --save-dev tap-spec
```

## Usage

### Streaming

```js
var test = require('tape');
var tapSpec = require('tap-spec');

test.createStream()
  .pipe(tapSpec())
  .pipe(process.stdout);
```

### CLI

**package.json**

```json
{
  "name": "module-name",
  "scripts": {
    "test": "node ./test/tap-test.js | tap-spec"
  }
}
```

Then run with `npm test`

**Terminal**

```
tape test/index.js | node_modules/.bin/tap-spec
```

**Testling**

```
npm install testling -g
testling test/index.js | node_modules/.bin/tap-spec
```

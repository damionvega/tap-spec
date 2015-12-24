Formatted TAP output like Mocha's spec reporter

![iterm - 2 bash - may 29 2015 at 10 17 am screen shot](https://cloud.githubusercontent.com/assets/974723/7888261/03366236-05ec-11e5-9f94-d9c2707526b7.png)

## Install
This fork:
```
npm install --save-dev git+https://github.com/damionjn/tap-spec.git
```

Original tap-spec:
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

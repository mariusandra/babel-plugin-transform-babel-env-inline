Adapted from https://github.com/babel/babili/tree/master/packages/babel-plugin-transform-node-env-inline

# babel-plugin-transform-babel-env-inline

Inline the `BABEL_ENV` environment variable and if it's a part of a binary expression
(eg. `process.env.BABEL_ENV === "react"`) then statically evaluate and replace it.

## Example

**In**

```javascript
process.env.BABEL_ENV === "react";
process.env.BABEL_ENV === "inferno";
```

**Out**

```sh
BABEL_ENV=react babel in.js --plugins transform-babel-env-inline
```

```javascript
true;
false;
```

## Installation

```sh
npm install babel-plugin-transform-babel-env-inline
```

## Usage

### Via `.babelrc` (Recommended)

**.babelrc**

```json
{
  "plugins": ["transform-babel-env-inline"]
}
```

### Via CLI

```sh
babel --plugins transform-babel-env-inline script.js
```

### Via Node API

```javascript
require("babel-core").transform("code", {
  plugins: ["transform-babel-env-inline"]
});
```

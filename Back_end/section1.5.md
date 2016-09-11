# babel

### USING ES6/ES2015 IN A EXPRESS

```
$ cd myApp
$ npm install eslint@3.x babel-eslint@6 babel-preset-es2015 babel-preset-stage-0 --save-dev
```

##### .babelrc

```
{
  "presets": [
    "es2015",
    "stage-0"
  ]
}

```

##### .eslintrc

```
{
  "parser": "babel-eslint",

  "env": {
  	"node": true,
  	"es6": true
  },

  "rules":{
  	"vars-on-top": 2,
  	"no-undef": 2
  }
}
```

##### app.js

add `"use strict";` on the top of file

##### package.json

```
"scripts": {
  "lint": "eslint app.js",
  "start": "babel-node ./bin/www",
  "auto-start": "nodemon --exec \"npm run lint && npm start\" --ignore public/js"
}
```

##### start app
```
$ npm run auto-start
```

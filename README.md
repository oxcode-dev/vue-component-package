# Publish Vue Component on NPM using Laravel-mix

### Create NPM Account
`npm addUser`

### To login
`npm login`

### To Know if you logged
`npm whoami`

### Create new project.
`mkdir vue-component`

### Initiate Git
`git init`

### Initiate NPM
`npm init`

### Create a folder e.g. resources
`mkdir resources`

### Create vue component
`touch HelloWorld.vue`

### Create index.js file within the resources created
`cd resources && touch index.js`

### Import the component into the index.js file
```
import HelloWorld from './HelloWorld'

export default HelloWorld;
```

### Install laravel-mix and cross-env
`npm install laravel-mix && npm install cross-env`

### Copy the scripts below to package.json
```
"scripts": {
    "dev": "npm run development",
    "development": "cross-env NODE_ENV=development node_modules/webpack/bin/webpack.js --progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js",
    "watch": "npm run development -- --watch",
    "hot": "cross-env NODE_ENV=development node_modules/webpack-dev-server/bin/webpack-dev-server.js --inline --hot --config=node_modules/laravel-mix/setup/webpack.config.js",
    "prod": "npm run production",
    "production": "cross-env NODE_ENV=production node_modules/webpack/bin/webpack.js --no-progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js"
  },
```

### Create webpack.mix.js file
`touch webpack.mix.js`

### Copy the below code to webpack.mix.js
```
const mix = require('laravel-mix');

mix.js('./src/index.js', 'dist/index.js');

mix.webpackConfig({
    output: {
        libraryTarget: 'umd',
    }
});
```

### Publish your package or component
`npm publish`

### Upgrade NPM package version
```
npm version patch 0.0.2
npm version minor 0.2.0
npm version major 2.0.0
```

# Example using [Yarn](https://yarnpkg.com/en/) workspaces in an [Expo](https://expo.io/) app with [Lerna](https://lerna.js.org/)

## Start
$ git clone https://github.com/stephenhandley/expoyarnlerna
$ cd expoyarnlerna
$ yarn
$ yarn bootstrap
$ yarn build
$ yarn start:app

## Rough process
1. Setup new project with Lerna
2. Create Expo app in `packages/app`
3. Create shared package in `packages/shared`
4. Follow process described [here](https://github.com/expo/expo/tree/master/packages/expo-yarn-workspaces) to enable Yarn workspaces within Expo app
5. Add babel deps to top level package in order to build shared directories
```
yarn add --dev -W @babel/cli @babel/core @babel/preset-react @babel/preset-env babel-preset-expo babel-loader webpack
```
Without this you'll see Expo app barf on JSX, etc.
```
Module parse failed: Unexpected token (4:9)
You may need an appropriate loader to handle this file type.
```
6. Make `package.json` and `babel.config.js` files parallel the ones here

## Versions
Expo 34.0.1
Lerna 3.16.4
Yarn 1.12.3

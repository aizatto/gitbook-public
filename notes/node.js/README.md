# Node.js

* [Reference: JavaScript](https://app.gitbook.com/js/)
* [https://devcenter.heroku.com/articles/node-best-practices](https://devcenter.heroku.com/articles/node-best-practices)
* [https://david-dm.org/zce/itcast-tms?type=dev](https://david-dm.org/zce/itcast-tms?type=dev)
* [https://github.com/observing/pre-commit](https://github.com/observing/pre-commit)

## tooling

```bash
yarn add -g prettyjson
```

[https://npmcompare.com/compare/jsontool,prettyprint](https://npmcompare.com/compare/jsontool,prettyprint)

## yarn vs npm

| yarn               | npm                 |
| ------------------ | ------------------- |
| yarn               | npm install         |
| yarn add `package` | npm -i -S `package` |

* [https://yarnpkg.com/](https://yarnpkg.com)
* [https://www.sitepoint.com/yarn-vs-npm/](https://www.sitepoint.com/yarn-vs-npm/)
* [https://yarnpkg.com/lang/en/docs/migrating-from-npm/](https://yarnpkg.com/lang/en/docs/migrating-from-npm/)
* [https://shift.infinite.red/npm-vs-yarn-cheat-sheet-8755b092e5cc](https://shift.infinite.red/npm-vs-yarn-cheat-sheet-8755b092e5cc)

## ORM

* [http://docs.sequelizejs.com](http://docs.sequelizejs.com)
* [http://bookshelfjs.org](http://bookshelfjs.org)

## nvm

```bash
nvm ls nvm use system
```

## gitignore

```
node_modules
```

## `package.json`

Environment variables are passed into the `scripts`.

This can be tested via:

```javascript
{
  scripts: {
    "env": "env | grep NODE"
  }
}
```

Run

```bash
yarn run env
NODE_ENV=production yarn run env
```

## express

* [https://expressjs.com/en/guide/debugging.html](https://expressjs.com/en/guide/debugging.html)

```
  DEBUG=express:* yarn start
  DEBUG=express-start yarn start
  DEBUG=knex:* yarn start
  DEBUG=knex:query yarn start
  DEBUG=knex:tx yarn start
```

[https://github.com/node-inspector/node-inspector](https://github.com/node-inspector/node-inspector)

## `String`s

[https://stackoverflow.com/questions/16293923/does-v8-have-unicode-support](https://stackoverflow.com/questions/16293923/does-v8-have-unicode-support) [https://github.com/v8/v8/blob/master/include/v8.h](https://github.com/v8/v8/blob/master/include/v8.h)

##

[https://nodejs.org/api/buffer.html#buffer\_buffers\_and\_character\_encodings](https://nodejs.org/api/buffer.html#buffer\_buffers\_and\_character\_encodings) [https://nodejs.org/dist/latest-v4.x/docs/api/buffer.html#buffer\_buffers\_and\_character\_encodings](https://nodejs.org/dist/latest-v4.x/docs/api/buffer.html#buffer\_buffers\_and\_character\_encodings)

## Mocha

mocha -g 'grep patern for function' file

## grunt

grunt --tasks .

## Bootstrapping a project

* Use [Yarn](https://yarnpkg.com/en/docs/install)
* Install [eslint](http://eslint.org/docs/user-guide/getting-started)
* Install [flow](https://flow.org/en/docs/install/)
* Install [pre-commit](https://www.npmjs.com/package/pre-commit) hooks

```bash
brew install yarn
yarn add --dev babel-cli babel-preset-flow eslint flow-bin pre-commit
yarn run eslint -- --init
yarn run flow init
```

## Cons

* No consistency in one app from another.

## Server Side

* Run latest ES code

## Client Side

* Transpile it to a version browsers can use
* Has to use transpiled server side version

## Support

[https://github.com/nodejs/Release](https://github.com/nodejs/Release)

| version | Support           |
| ------- | ----------------- |
| 8.10    | AWS Lamba Support |

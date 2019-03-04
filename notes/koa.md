# Koa

[https://npmcompare.com/compare/connect,express,hapi,koa](https://npmcompare.com/compare/connect,express,hapi,koa)

| Feature | Koa | Express | Hapi |
| :--- | :--- | :--- | :--- |
| async/await | yes | no | no |
| Routing | no | yes | yes |
| Templating | no | yes |  |

* Koa vs Express
  * [https://github.com/koajs/koa/blob/master/docs/koa-vs-express.md](https://github.com/koajs/koa/blob/master/docs/koa-vs-express.md)
  * Koa has async/await support
  * Express is supposed to have it in v5
  * v5 was first mentioned in July 2014
    * [https://github.com/expressjs/express/pull/2237](https://github.com/expressjs/express/pull/2237)
  * Alternatives
    * [https://www.npmjs.com/package/@awaitjs/express](https://www.npmjs.com/package/@awaitjs/express)
  * Koa does not have
    * routes, use a plugin instead
    * templating
    * sending files
* Koa vs Hapi
  * Hapi does not have async/await support
    * [https://github.com/hapijs/hapi/issues/3429](https://github.com/hapijs/hapi/issues/3429)
    * [https://github.com/hapijs/hapi/pull/3486](https://github.com/hapijs/hapi/pull/3486)




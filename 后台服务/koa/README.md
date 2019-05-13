### koa

* 安装方式
    * `npm install koa --save-dev`

* 相关插件
    * `koa-router` 路由
    * `koa-json` json 格式显示
    * `koa-bodyparser` body 解析器

* 服务器使用方法
```js
// 实例化koa
const Koa = require('koa');
const app = new Koa();

// 实例化路由及配置
const Router = require('koa-router');
const router = new Router();
app.use(router.routes()).use(router.allowedMethods());

// body 数据解析配置
const bodyParser = require('koa-bodyparser')
app.use(bodyParser())

// 路由
router.get('/', async ctx => {
    ctx.body = { msg: 'Hello Koa Interfaces'};
});

// 配置路由地址
const users = require('./routes/api/users');
router.use('/api/users', users);


const port = process.env.PORT || 5000;

app.listen(port, () => {
    console.log(`server started on ${port}`);
});
```

* 路由控制
```js
const Router = require('koa-router');
const router = new Router();

const User = require('../../models/User')

router.get('/test', async ctx => {
    ctx.status = 200;
    ctx.body = { msg: 'users works....'}
})

router.post('/register', async ctx => {
    let body = ctx.request.body
    console.log(body)
})

module.exports = router.routes()
```
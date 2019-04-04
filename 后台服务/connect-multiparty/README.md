### connect-multiparty

* 安装方式
    * `npm install connect-multiparty --save-dev`

* 使用方式

```js
// 在 server.js 内配置
// 上传文件
const multiparty = require('connect-multiparty')
// 定义上传的路径
app.use(multiparty({uploadDir: './updata/'}))
```
```js
// 在路由内使用
const express = require('express')
const router = express.Router()

const multiparty = require('connect-multiparty')
const multipartyMiddeware = multiparty()

router.post('/upload', multipartyMiddeware, (req, res) => {
    console.log(req.files)
    res.json({msg: 'success'})
})
```
### express

* 安装方式
    * `npm install express --save-dev`

* 服务器使用方法
```js
// 引入 express 插件
const express = require('express')
// 实例话一个 express 项目
const app = express()

// 初始化端口
const port = process.env.PORT || 5000

// 创建一个 get 请求接口
app.get('/', (req,res) => {
    res.send('接口成功')
})

// 开启监听
app.listen(port, () => {
    console.log(`Server Running Port On ${port}`)
})
```

* Router 的使用
```js
// 引入 express 插件
const express = require('express')
// 获取 router 实例
const router = express.Router()

// 添加 get 方法及访问地址
// 可以有其他方法 比如 post pull delete
// req 为客户端发送的信息
    // req.headers 内容为 header
    // req.params 内容为 /:param
    // req.query 内容为 ?param=var
    // req.body 内容为 body
// res 为发送给客户端的信息
    // res.status(200) 状态
    // res.send(str) 文本内容
    // res.json(json) json内容
router.get('/test', (req,res) => {
    res.send("users api test success")
})

// 把定义完的 router 公布给 server
module.exports = router

// ================== server.js 内使用 ======================
// 引入 express 插件
const express = require('express')
// 实例话一个 express 项目
const app = express()
// 引入 router
const router = require('./router/path')
// 使用 router
app.use('/api/user', router)
```
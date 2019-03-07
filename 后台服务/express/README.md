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
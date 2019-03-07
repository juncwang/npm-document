### mongoose

* 安装方式
    * `npm install mongoose --save-dev`

```js
// 引入 mongoose 插件
const mongoose = require('mongoose')
// 定义链接地址
const mongoURI = 'mongodb://数据库管理员账户:密码@127.0.0.1:27017/表名?authSource=admin'
// 链接数据库
mongoose.connect(mongoURI, { useNewUrlParser: true })
    .then(() => {
        console.log("MongoDB Connect Success")
    })
    .catch(() => {
        console.log("MongoDB Connect Failure")
    })
```
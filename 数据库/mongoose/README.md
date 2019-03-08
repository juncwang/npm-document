### mongoose

* 安装方式
    * `npm install mongoose --save-dev`

* 使用链接数据库
```js
// 引入 mongoose 插件
const mongoose = require('mongoose')
// 定义链接地址
const mongoURI = 'mongodb://数据库管理员账户:密码@127.0.0.1:27017/表名?authSource=admin'
// 链接数据库
mongoose.connect(mongoURI, { useNewUrlParser: true })
    .then(() => console.log("MongoDB Connect Success"))
    .catch((err) => console.log(`MongoDB Connect Failure ${err}`))
```

* Schema 创建
```js
const mongoose = require('mongoose')
const Schema = mongoose.Schema

const UserSchema = new Schema({
    // 数据名称
    username: {
        // 数据类型
        type: String,
        // 必须有的值
        // default: xxx 表示如果没有放入 xxx 默认值
        // 不写这行表示可以不需要这个数据
        required: true
    }
})

// 建立数据表模型并公布出去
module.exports = User = mongoose.model('users', UserSchema)
```

* 添加数据
```js
const User = require('./模型地址')
const newUser = new User({模型数据})

// 保存新数据
newUser.save()
    .then(user => {})
    .catch(err => {})
```

* 删除数据
```js
const User = require('./模型地址')

// 根据属性查找一个数据并删除
User.findOneAndRemove({ att })
    .then(user => {
        user.save()
            .then(user => {})
            .catch(err => {})
    })
    .catch(err => {})
```

* 修改数据
```js
const User = require('./模型地址')
const newUser = new User({模型数据})

// 根据属性查找一条数据并修改
User.findOneAndUpdate(
    { att }, // 根据属性进行查找
    { $set: newUser }, // 需要更新的数据
    { new: true }   // 是否是新的
)
    .then(user => {})
    .catch(err => {})
```

* 查询数据
```js
const User = require('./模型地址')

// 根据属性查询一条有以下属性的数据
User.findOne(att})
    .then(user => {})
    .catch(err => {})

// 根据 id 查找数据
User.findById(id)
    .then(user => {})
    .catch(err => {})
```
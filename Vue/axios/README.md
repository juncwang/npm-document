### axios

* 安装方式
    * `npm install axios --save-dev`

* 使用 axios 进行跨域请求
    * 在 `main.js` 内配置如下
    * `import axios from 'axios'` 全局引入
    * `axios.defaults.headers.common['token'] = 'f4c902c9ae5a2a9d8f84868ad064e706'` 配置头文件内的 token
    * `axios.defaults.headers.post['Content-Type'] = 'application/x-www-form-urlencoded'` 配置头文件内的 content-type
    * `Vue.prototype.$axios = axios` 把 axios 给予 vue

* 使用 axios 拦截请求
```js
// 新建一个 axios.js 文件
import axios from 'axios'

// 发出请求时拦截
axios.interceptors.request.use(config => {
    // ********
    // 拦截请求时, 想要执行的语句
    // config 为配置文件
    // ********
    return config
}, error => {
    return Promise.reject(error)
})

// 接收请求时拦截
axios.interceptors.response.use(response => {
    // ********
    // 拦截接收时, 想要执行的语句
    // response 为返回文件
    // ********
    return response
}, error => {
    return Promise.reject(error)
})

export default axios
```

```js
this.$axios.post("/apis/test/testToken.php",{
username:"juncwang",
password:"123456"
})
.then(data => console.log(data))
```
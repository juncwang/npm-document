### npm-document

* 下载地址 `http://nodejs.cn/`
    * 下载 `nodejs` 安装后, 即可使用 `npm` 命令

* `npm` 的镜像替换成淘宝
    * `npm config set registry http://registry.npm.taobao.org/` 运行命令即可替换

* 安装 `cnpm` 方法
    * `npm install cnpm -g --registry=http://registry.npm.taobao.org/` 运行命令即可替换

* 初始化项目生成配置文件 `package.json`
    * `npm init`

* 安装插件方法
    * `npm install 插件名称`
        * 后面加 `-g` 为全局安装
        * 后面加 `--save-dev` 为项目内安装并且写入 `package.json` 配置文件
            * 写入后项目在其他机器上应用时, 仅需执行 `npm install` 命令即可把配置文件内的所有插件重新安装 

### npm-plugin

* 后台服务
    * `node` 后台服务程序
    * `nodemon` 后台服务程序 (调试后台程序使用)
    * `express` node 的一个网络框架
    * `body-parser` 解析 body 的工具

* 数据库
    * `mongoose` 链接 `mongoDB` 数据库使用
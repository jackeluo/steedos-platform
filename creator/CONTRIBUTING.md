# 开发指引

### 运行项目源码
- [安装Meteor](https://www.meteor.com/install)
- [安装yarn](https://yarnpkg.com/zh-Hant/)
- 将项目克隆到本地
- 进入项目文件夹
- 执行 yarn ，安装依赖包。
- 执行 meteor
- 使用浏览器访问 https://localhost:3000
- 点击创建企业，注册企业账户

### 安装MongoDB数据库
- [安装MongoDB](https://docs.mongodb.com/manual/administration/install-community/)
- 启动MongoDB服务
- 设定环境变量
```
export MONGO_URL=mongodb://127.0.0.1/steedos
```

### 编译并运行
```
export TOOL_NODE_FLAGS="--max-old-space-size=3800"
yarn run build
cd .dist
yarn
yarn start
```

### 发布版本
**版本发布前准备**
- 需先修改 .dist/package.json 中的版本号。
- 因为要发布空的steedos-server，需先修改 .meteor/packages，注释app相关的package
- 新增的meteor package 项目，如果有Npm.depends部分，需要将node package添加到package.json及.dist/package.json

> 注意发版本是在项目根目录发，不是在.dist中

**发布脚本**
```
yarn run login
yarn run pub
```
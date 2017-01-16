## npm 
- node package manager  node包管理器
- 包由模块组成

## 初始化package.json 文件
```
npm init -y
```
> 记录依赖默认是json格式，json不能有注释，否则会报错

## 安装
下面以安装express为例

- 全局安装加 -g

```
npm install express -g 

```

- 依赖信息写入package.json文件
```
npm install express --save
```

- 依赖信息写入package.json文件（开发依赖，生产环境不需要使用到的包，比如less等一些工具类依赖包）
```
npm install less --save-dev 
```

```
  //依赖包  
  "dependencies": {
    "body-parser": "^1.15.2",
    "cookie-parser": "^1.4.3",
    "ejs": "^2.5.5",
    "express": "^4.14.0",
    "express-session": "^1.14.0",
    "jquery": "^1.11.3"
  },
  //开发依赖包
  "devDependencies": {
    "less": "^2.7.2"
  }
```

- 默认安装的是包的最新稳定版本，安装是也可以指定安装特定的版本
安装jquery 1.11.3版本
```
npm install jquery@1.11.3   --save
```

- 查看安装的版本信息
查看jquery版本的信息
```
npm info jquery 
```
- 安装依赖

如果已经存在package.json文件，会将开发依赖和依赖全部下载
```
npm  install 
```

- 查看全局安装的路径
```
npm root -g
```

## 卸载
```
npm install less
```

> 这样卸载之后，`node_modules` 目录下less包相关的文件已经删除，但是package.json文件中less的信息还在，需要手动删除。


## 配置npm内网源
```
npm config set registry  "http://172.18.0.18"
```

## npm 源信息管理工具

- 安装nrm
```
nrm install nrm -g 
```

- 添加源
```
nrm add mysource http://172.16.0.99
```

- 查看源
```
nrm ls
```

`*` 号代表当前正在使用的源

```
$ nrm ls

  npm ---- https://registry.npmjs.org/
* cnpm --- http://r.cnpmjs.org/
  taobao - https://registry.npm.taobao.org/
  nj ----- https://registry.nodejitsu.com/
  rednpm - http://registry.mirror.cqupt.edu.cn/
  npmMirror  https://skimdb.npmjs.com/registry/
  edunpm - http://registry.enpmjs.org/
  mysource  http://172.18.0.199/
```
- 切换源
```
nrm use mysource 
```

## 发布包 
// todo











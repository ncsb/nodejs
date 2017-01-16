
# express中使用 session 和 cookie



## session 

依赖模块

```
npm install express-session --save

```

使用

```
var session = require('express-session');

app.use(session({
    resave: true,  
    saveUninitialized: true,
    secret: 'ncsb'
}));
// resave  每次访问服务器的时候都会重新保存一次session
// saveUninitialized     true保存未初始化的session,false 不保存
// secret  用来加密cookie的秘钥

```

### session的操作： 设置和删除都是通过request.session对象

- 设置和修改session 存在修改，不存在新增

```
request.session.username = 'zq';
```

- 删除session ，直接设置为null 或者 ''

```
request.session.username = '';
```


## cookie

依赖模块
```
npm install cookie-parser  --save

```

使用
```
var cookieParser = require('cookie-parser');
app.use(cookieParser());

```

###  express在服务端操作cookie

获取cookie使用request对象

```
request.cookies

```


设置cookie使用response对象

```
response.cookie('username','zq');

```


设置cookie的domain,path,expire,max-age

- domain
```
response.cookie('name','zq',{domain:'a.zq.com'});
```

- path 默认是根路径/ 全局有效, 可以指定某个路径
```
 response.cookie('name','zq',{path:'/read1'});
```


- expire  过期时间
过期时间是一个确定的日期
```
 response.cookie('name','zq',{expires:new Date(Date.now()+10*1000)});
```

Date.now() 得到的是一个单位为毫秒的时间戳


-  maxAge  有效期，单位是毫秒，有效期是多少毫秒
在前端设置的键是max-age 

```
response.cookie('name','zq',{maxAge:10*1000});

```





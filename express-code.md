## express 代码片段

###  express init 
```
var express = require('express');
var app = express();
app.use(function(request,response){
    // todo 
    next();
});
app.get('/',function(request,response){
    response.end('response end...');
});

```


### express ejs 
```
var ejs =  require('ejs');
// 设置模板文件的根目录
app.set('views',__dirname+'/views');

// 设置模板文件的后缀名为html
app.set('view engine','html');

// 后缀为html的文件使用ejs解析
app.engine('html',ejs.__express);

...
//渲染模板调用
//response.render('signup.html',{title:"注册"});
response.render('signup',{title:"注册"});

```


### express cookie

统计访问次数,express中操作cookie 的 demo
```
var express = require('express');
//使用cookie-parser模块操作cookie
var cookieParser = require('cookie-parser');
var app = express();
//使用cookie-parser
app.use(cookieParser());

app.get('/visit',function(request,response){
   //获取cookie对象  var cookieObj = request.cookies;
   //底层实现  
   // var cookie = request.headers.cookie;
   //var cookieObj = queryString.parse(cookie,'; ');
   var cookieObj = request.cookies;
   
   console.log(cookieObj);
   if(cookieObj && cookieObj.count){
        cookieObj.count++;
   }else{
     cookieObj.count = 1;
   }
   //设置cookie对象
   response.cookie('count',cookieObj.count);
   
   response.send('this is '+cookieObj.count+' come here!');
});
app.listen(80);
```

pure code 

```
var express = require('express');
var cookieParser = require('cookie-parser');
var app = express();
app.use(cookieParser());
app.get('/visit',function(request,response){
   var cookieObj = request.cookies;
   if(cookieObj && cookieObj.count){
        cookieObj.count++;
   }else{
     cookieObj.count = 1;
   }
   response.cookie('count',cookieObj.count);
   response.send('this is '+cookieObj.count+' come here!');
});
app.listen(80);
```
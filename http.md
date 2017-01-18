


## curl  发送请求
```
$ curl -X POST --data '{"name":"angular权威指南","price":99,"img":"https://public/1.png"}' -H "Content-Type:application/json" http://localhost:8080/books
```
- -X  请求方式
- `--data`  请求体
- -H 请求头
可以使用curl模拟get，post请求，还可以设置请求头，请求内容的类型，测试某些接口还是挺方便的。

## 跨域 
> CORS Cross-Origin Resource Sharing 跨域资源共享
 
 
<https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Access_control_CORS>

### express框架中设置允许跨域请求和跨域请求的方式
Access-Control-Allow-Origin  允许请求的源
Access-Control-Allow-Methods 允许请求的方法
```
app.use(function(req,res,next){
    //访问控制 允许哪个域来请求我的服务器接口
    res.setHeader('Access-Control-Allow-Origin','http://localhost:8080');
    //允许跨域请求的方法
    res.setHeader('Access-Control-Allow-Methods','GET,POST,PUT,DELETE');
    next();
});
```

---

- 跨域请求可以使用cookie 和session吗？ 待测试
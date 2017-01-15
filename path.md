
## 路径相关
path 是node中的内置模块，主要是对路径进行处理

```
var path = require('path');
console.log(path);

```

```
{ 
resolve: [Function: resolve],
  normalize: [Function: normaliz
  isAbsolute: [Function: isAbsol
  join: [Function: join],
  relative: [Function: relative]
  _makeLong: [Function: _makeLon
  dirname: [Function: dirname],
  basename: [Function: basename]
  extname: [Function: extname],
  format: [Function: format],
  parse: [Function: parse],
  sep: '\\',
  delimiter: ';',
  win32: [Circular],
  posix:
   { resolve: [Function: resolve
     normalize: [Function: norma
     isAbsolute: [Function: isAb
     join: [Function: join],
     relative: [Function: relati
     _makeLong: [Function: _make
     dirname: [Function: dirname
     basename: [Function: basena
     extname: [Function: extname
     format: [Function: format],
     parse: [Function: parse],
     sep: '/',
     delimiter: ':',
     win32: [Circular],
     posix: [Circular] }
   }
```
上面是模块中包含的方法，win7 node7.4.0,一下例子是path.js文件所在的目录为d:\wamp\www\node12\nodejs\tmp
- resolve 
```
//不传参数，会得打当前文件所在的目录
console.log( path.resolve() ); // d:\wamp\www\node12\nodejs\tmp
//上面等价于 
console.log(__dirname); 

//传参数会使用当前目录+传入的参数                                  
console.log(path.resolve('public'));// d:\wamp\www\node12\nodejs\tmp\public
// 上面等价于
console.log(__dirname+'/'+'public');

console.log(path.resolve('public','test','server.js'));//d:\wamp\www\node12\nodejs\tmp\public\test\server.js

```
- join

```
```
- dirname
- basename
- extname 
- parse
- sep 路径分隔符号，是一个二属性不是方法

path模块下的方法，与处理的路径或者文件和目录是否存在没有关系。

### __dirname
当前文件目录的绝对路径
不是global上的属性，是外面函数的形参，在文件中可以直接访问


### __filename
当前文件的绝对路径




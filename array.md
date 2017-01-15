

数组的几个遍历的方法：forEach,map,filter,find。其中find是ES6的，其它的都是ES5的。

## forEach 遍历
forEach可以对数组进行遍历，没有返回值

```
var arr = [1,2,3,4];
// forEach  返回值为undefined，不影响原数组的元素,不可以终止
var a = arr.forEach(function(item){
    console.log(111111);//数组有几个元素输出几次
    return false;
});
console.log(a);
console.log(arr);
```

## map  修改
map  返回修改后的数组，不影响原数组的元素
```
 var arr = [1,2,3,4];
 // forEach  返回值为新的数组，不影响原数组的元素,不可以终止
var a = arr.map(function(item){
    console.log(111111);//数组有几个元素输出几次
    return item+'5';
});
 console.log(a);
 console.log(arr);
```
## filter  过滤(可以删除数组的元素)
回到函数返回值为true保留改，为false为删除
返回值为过滤后的数组

```
 var arr = [1,2,3,4];
 //不影响原数组，返回过滤后的数组
 var a = arr.filter(function(item){
     console.log(11111111); //数组有几个元素就会输出几次
     return item%2==0;// 返回true保留，false删除
 });
 console.log(a);
 console.log(arr);
```

## find   查找
回调函数返回值为true
返回查找到的元素 

```
 var arr = [1,2,3,4];
 //不影响原数组，返回找到的元素
 var a = arr.find(function(item){
     console.log(11111111);//返回true终止循环
     return item==3;//找到返回true,遍历终止，
 });
 console.log(a);
 console.log(arr);
```

> 上面五个方法除了有各自的应用场景之外，还可以传第二个参数，用来改变this指向。


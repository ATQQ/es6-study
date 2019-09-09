# 12.1 参数的默认值

ES6 之前，不能直接为函数的参数指定默认值，只能采用变通的方法。
```js
function add(x, y) {
    x=x||1;
    y=y||2;
    return x+y;
}
console.log(add());//3
```

ES6 允许为函数的参数设置默认值，即直接写在参数定义的后面。
```js
function add(x=1,y=2){
    return x+y;
}
console.log(add());//3
```
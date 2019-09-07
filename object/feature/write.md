# 6.2 新的书写方式

ES6 允许直接写入变量和函数，作为对象的属性和方法。这样的书写更加简洁。
## ES5写法
```js
let name="小明";
let age=19;
let obj1={
    name:name,
    age:age,
    sayHello:function () {
        console.log('hello es5');
    }
}
```

## ES6写法
```js
let obj2={
    name,
    age,
    sayHello(){
        console.log("hello es6");
    }
}
```

这种写法用于函数的返回值，将会非常方便。
```js
function getRectangle(){
    let w=5;
    let l=10;
    return {w,l};
}
getRectangle();
```
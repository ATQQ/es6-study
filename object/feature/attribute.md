# 6.3 属性名的表达式

## old
js中定义属性的方法
```js
let obj={};
// 第一种
obj.a='hello';

// 第二种
obj['b'+'b']='hello';
```

但是，如果使用字面量方式定义对象（使用大括号），在 ES5 中只能使用第一种（标识符）定义属性。
```js
// 第三种
let obj={
    a:1,
    'b':2
}
```

## new
ES6 允许字面量定义对象时，用第二种（表达式）作为对象的属性名，即把表达式放在方括号内。
```js
let key = 'name';
let obj = {
    [key]: '小黑'
}
obj.name//小黑
```
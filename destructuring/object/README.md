# 3.2 对象的解构

## 简单用法
```js
    let a,b;
    ({ a, b } = { a: 2, b: 3 })
    console.log(a,b);//2,3;

    //变量名与属性名一致
    let {name}={name:'小明',age:18};
    console.log(name);//小明

    // 变量名与属性名不一致
    let {a:name,b:age}={a:'小明',b:18};
    console.log(name,age);//小明 18
```

## 如果解构失败，变量的值等于undefined。
```js
let {a}={b:2};
a;//undefined
```

## 多层嵌套示例
```js
function fn() {
    return {
        name: '小明',
        userList: [
            { name: '小红' }
        ]
    }
}

let res = fn();
let { name: person, userList: [{ name: otherPerson }] } = res;

console.log(person, otherPerson);//小明 小红
```

## 如果解构模式是嵌套的对象，而且子对象所在的父属性不存在，那么将会报错。
```js
let {a: {b}} = {b: 666};
```

## 设置默认值
```js
let {a=1}={a:3};
```

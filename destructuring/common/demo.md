# 3.4 常见用途

## 交换两个变量的值
```js
let a = 1;
let b = 2;

[a, b] = [b, a];
```

## 取函数返回值
```js
// 返回数组
function f1(){
    return [1,2,3];
}
let [a,b,c]=f1();

// 返回对象
function f2(){
    return {
        name:'小明',
        age:18
    }
}
let {name,age}=f2();
```

## 提取ajax回调的JSON 数据
```js
function ajax(){
    return {
        code:200,
        errMsg:'success',
        data:{
            userList:[
                {name:'小明',age:18},
                // ...more data
            ]
        }
    }
}

let {code,data:{userList}}=ajax();
```

## 加载外部模块的指定方法或变量
```js
const { helllo, a } = require("source");
```

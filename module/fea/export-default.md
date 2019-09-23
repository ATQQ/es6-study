# export default

当使用export导出的模块,使用import命令的时候，用户需要知道所要加载的变量名或函数名，否则无法加载。但是，用户肯定希望快速上手，未必愿意阅读文档，去了解模块有哪些属性和方法。

为了给用户提供方便，让他们不用阅读文档就能加载模块，就要用到export default命令，为模块指定默认输出。

## 简单用法
### 导出匿名函数
#### export.js
```js
export default function(){
    console.log("success");
}
```
#### import.js
```js
import a from "./export.js"
a();//success
```
### 导出非匿名函数
#### export.js
```js
const hello =()=>{
    console.log("hello");
}
export default hello;
```
#### import.js
```js
import any from "./export.js"
any();//hello
```

## 综合
### export.js
```js
let a=1,b=2;

const sum=(a,b)=>a+b;

const obj={
    name:"小明",
    age:18
}
export default{
    a,
    b,
    sum,
    obj
}
```
### import.js
* demo1
```js
import {a,sum} from "./export.js"
console.log(a,sum(2,3));//1 5
```

* demo2
```js
import all from "./export.js"
console.log(all.sum(1,1));//2
```
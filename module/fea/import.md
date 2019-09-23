# import

使用export命令定义了模块的对外接口以后，其他 JS 文件就可以通过import命令加载这个模块。

## 简单用法
### demo.js (export部分变量)
```js
let a=1,b=2;
export{
    a,b
}
```
### demo2.js (引入导出的变量)
```js
import { a, b } from './demo1.js';
console.log(a,b);//1 2
```
### demo3.js (重命名导入的参数)
```js
import { a as hello, b } from './demo1.js';
console.log(hello,b);//1 2
```
## import命令输入的变量都是只读的
```js
import {a} from './demo1.js'
a = {}; // Syntax Error : 'a' is read-only;
```
如果引入的是对象则可以修改其属性
```js
// export.js
let obj1={a:2}
export{
    obj1
}

//import.js
import {obj1} from ",/export.js"
obj1.a=3;
console.log(obj1);//{ a: 3 }
```
**注意，import命令具有提升效果，会提升到整个模块的头部，首先执行。**

## 执行所加载的模块
```js
import 'start.js';
```

## 整体加载模块
## export.js
```js
let a = 1;
let add = (a, b) => a + b;

export {
    add,
    a
}
```
## import.js
```js
import * as m1 from './export.js';
console.log(m1.a);//1
console.log(m1.add(1,2));//3
```

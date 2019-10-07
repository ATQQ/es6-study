# export与import复合
如果在一个模块之中，先输入后输出同一个模块，import语句可以与export语句写在一起。
```js
export { m1, m2 } from 'module';

// 等价于
import { m1, m2 } from 'module';
export { m1, m2 };
```
## 接口改名
```js
export { m1 as hello } from 'module';
```
## 整体输出
```js
export * from "module"
```
## 具名接口改为默认接口
```js
export {es6 as default} from "module";
// 等同于
import { es6 } from 'module';
export default es6;
```

## 默认接口改名为具名接口
```js
import {default as es6} from "module";
```

## 应用场景举例
### 常量模块
```js
// user.js
const user={
    account:"123525",
    sex:"男",
    age:18
}
export {user}

//db.js
const db={
    url:"xxxx",
    useranme:"admin",
    password:123456,
    port:3306
}
export {db};

// const.js
export {db} from "./db"
export {user} from "./user"

// app.js
import {db,user} from "./const"
```
使用的时候直接加载const.js就能使用其它模块的常量

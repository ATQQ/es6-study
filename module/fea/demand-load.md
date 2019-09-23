# 按需加载

```js
// 报错
if (x === 2) {
  import MyModual from './myModual';
}

// node中的require
const path = './' + fileName;
const myModual = require(path);
```

如果import命令要取代 Node 的require方法，这就形成了一个障碍。因为require是运行时加载模块，import命令无法取代require的动态加载功能。

因此，有一个提案，建议引入import()函数，完成动态加载。
## import()
返回一个 Promise 对象
```js
import(`./section-modules/${name}.js`)
  .then(module => {
      ...
  })
  .catch(err => {
    console.log(err);
  });
```

## 条件加载
```js
if (condition) {
  import('module1').then(...);
} else {
  import('module1').then(...);
}
```
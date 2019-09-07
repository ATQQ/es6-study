# 5.3 替代apply

## 1.传递函数参数
### ES5 的写法
```js
function f(x, y, z) {
  // ...
}
var args = [0, 1, 2];
f.apply(null, args);
```

### ES6的写法
```js
function f(x, y, z) {
  // ...
}
let args = [0, 1, 2];
f(...args);
```

## 2.求数组最大值
### ES5 的写法
```js
Math.max.apply(null, [14, 3, 77])//77
```

### ES6 的写法
```js
Math.max(...[14, 3, 77])//77
```

### 等价于
```js
Math.max(14, 3, 77);//77
```
# 1.1.2 局部示例

## demo1
```js
!(function () {
    console.log(b);//undefined
    var b = 2;
})()
```
* 为什么会输出undefined,而不是报错?
* 此种也是变量提升造成的意料之外的结果,上面代码等同于下面.

```js
!(function () {
var b;
console.log(b);//undefined
b=2;
})()
```

## demo2
```js
var now = new Date();
function f() {
  console.log(now);
  if (false) {
    var now = 'hello world';
  }
}
f(); // undefined
```

f()执行后，输出结果为undefined，原因在于变量提升，导致内层的now变量覆盖了外层的now变量。
### 这就抛出来了一个问题,**什么是变量提升**?
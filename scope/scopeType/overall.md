# 1.1.1 全局示例

```js
var i=2;
for (var i = 0; i < 10; i++) {
}
console.log(i);//10
```
* 上面代码中，变量i只用来控制循环，但是循环结束后，它并没有消失，泄露成了全局变量。
* 这里就出现了意料之外的结果,此种结果是**变量提升**造成过的
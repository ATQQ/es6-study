# 2.3.2 例2

```js
let a=Symbol('symbolA');

let obj={
    [a]:1,
    a:2
}
// 各种写法的结果
obj.a   //2
obj['a']//2
obj[a]  //1
```
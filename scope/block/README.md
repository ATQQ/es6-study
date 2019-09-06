# 1.3 块级作用域

let实际上为 JavaScript 新增了块级作用域。
```js
function f() {
  let n = 5;
  if (true) {
    let n = 10;
  }
  console.log(n); // 5
}
f()
```
### 块级作用域使用方式 
```js
{
  //...code  
}
```
注意:使用 **var 声明变量**不受块级作用域限制,依旧会造成的变量提升,因此
引入了两个新的变量
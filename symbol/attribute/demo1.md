# 2.3.1 例1

**注意，Symbol 值作为对象属性名时，不能用点运算符。**
```js
const mySymbol = Symbol();
const a = {};

a.mySymbol = 'Hello!';
a[mySymbol] // undefined
a['mySymbol'] // "Hello!"
```
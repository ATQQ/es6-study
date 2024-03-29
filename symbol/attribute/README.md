# 2.3 属性名的 Symbol

由于每一个 Symbol 值都是不相等的，这意味着 Symbol 值可以作为标识符，用于对象的属性名，就能保证不会出现同名的属性。这对于一个对象由多个模块构成的情况非常有用，能防止某一个键被不小心改写或覆盖。

## 第一种写法
```js
let testKey=Symbol();
let a={};
a[testKey]='hello world';
```
## 第二种写法
```js
let testKey=Symbol();
let a={
    [testKey]:'hello world'
}
```
## 第三种写法
```js
let testKey=Symbol();
let a={};
Object.defineProperty(a,testKey,{value:'hello world'})

// 以上写法得到同样的结果
console.log(a[testKey]);//hello world
```
# 2.1 简单的用法

## 最简单的声明
```js
let a=Symbol();
console.log(a);//Symbol()
```

## 每一个都是独一无二
```js
let a=Symbol()
let b=Symbol()
console.log(a===b)//false
```
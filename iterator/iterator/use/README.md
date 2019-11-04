# 16.1 Iterator使用

>ES6 规定，默认的 Iterator 接口部署在数据结构的Symbol.iterator属性，或者说，一个数据结构只要具有Symbol.iterator属性，就可以认为是“可遍历的”（iterable）。Symbol.iterator属性本身是一个函数，就是当前数据结构默认的遍历器生成函数。执行这个函数，就会返回一个遍历器。至于属性名Symbol.iterator，它是一个表达式，返回Symbol对象的iterator属性

>ES6 的有些数据结构原生具备 Iterator 接口（比如数组），即不用任何处理，就可以被for...of循环遍历。

## 原生具备 Iterator 接口的数据结构有
* Array
* Map
* Set
* String
* TypedArray
* 函数的 arguments 对象
* NodeList 对象

## 简单用法 (数组)
```js
const arr = [1, 2, 3];
const fn = arr[Symbol.iterator]();
console.log(fn.next());//{value:1,done:false}}
console.log(fn.next());//{value:2,done:false}}
console.log(fn.next());//{value:3,done:false}}
console.log(fn.next());//{value:undefined,done:true}}
```

## 调用 Iterator 接口的场景(常见))
### 1.解构赋值
```js
let set=new Set().add(1).add(5).add("ada");
let [a,b,c]=set;
console.log(a,b,c);//1 5 ada
```

### 2.扩展运算符
```js
let str="1234";
let arr=[...str];
console.log(arr);//["1", "2", "3", "4"]
```


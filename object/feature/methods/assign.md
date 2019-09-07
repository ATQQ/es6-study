# 6.4.2 Object.assign()

## 描述
用于对象的合并，将源对象（source）的所有可枚举属性，复制到目标对象（target）,第一个参数是目标对象，后面的参数都是源对象。
```js
const a = { a: 1 };

const b1 = { b1: 1 };
const b2 = { b2: 2 };
const b3 = { b3: 3 };
Object.assign(a, b1,b2,b3);
a //{a: 1, b1: 1, b2: 2, b3: 3}
```

## 注意
如果目标对象与源对象有同名属性，或多个源对象有同名属性，则后面的属性会覆盖前面的属性。

```js
let a1={name:'小明',age:14}
let a2={name:'小红',address:'中国大陆'}
let a3=Object.assign({},a1,a2);
a3;//{name: "小红", age: 14, address: "中国大陆"}
```

## 常见用途

### 对象的拷贝
简单类型深拷贝,复杂类型浅拷贝,只拷贝源对象的自身属性（不拷贝继承属性），也不拷贝不可枚举的属性
```js
let obj1 = {
    name: '小明',
    age: 12
}
let obj2 = {};
Object.assign(obj2, obj1);
obj1.name = '小黑';
console.log('obj2 :', obj2);//{name: "小明", age: 12}
console.log('obj1 :', obj1);//{name: "小黑", age: 12}
```
### 为对象添加属性
```js
class Point {
constructor(x, y) {
  Object.assign(this, {x, y});
  }
}
```

### 为对象添加方法
```js
Object.assign(obj.prototype, {
      method1(a, b) {
      return a+b;
      },
      method2(a,b) {
      return a*b;
      }
});

// 等同于下面的写法
obj.prototype.method1 = function(a, b){
  return a+b;
  }
obj.prototype.method2 = function (a,b) {
  return a*b;
};
```
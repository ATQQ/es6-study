# 6.1 扩展运算符

>[ES2018](https://www.html.cn/archives/9990) 将扩展运算符(<code>...</code>)引入了对象。

## 拷贝对象
```js
const obj1={
    name:"小明",
    age:18
}    
const obj2={...obj1};
obj2.name='小红';
console.log('obj1 :', obj1);//{name: "小明", age: 19}
console.log('obj2 :', obj2);//{name: "小红", age: 19}
```

## 设置对象默认值
```js
let defaultObj = {
    class: 8,
    school: 'swpu'
}

let s1 = { ...defaultObj, name: '小红', age: 18 };
let s2 = { ...defaultObj, name: '小红', age: 19 };
console.log(s1);//{class: 8, school: "swpu", name: "小红", age: 18}
console.log(s2);//{class: 8, school: "swpu", name: "小红", age: 19}
```

## 合并对象
注意:展开简单运算法时是深拷贝,复杂类型是浅拷贝
```js
const testObj1 = { kind: 'pig' };
const testObj2 = { color: "red" };
let obj3 = { ...testObj1, ...testObj2 };
console.log(obj3);//{kind: "pig", color: "red"}
```
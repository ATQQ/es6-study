# 6.4.4 Object.fromEntries()

## 将键值对数组转为对象
```js
const obj=Object.fromEntries([
  ['name', '李华'],
  ['age', 18]
])
console.log(obj);//{name: "李华", age: 18}
```
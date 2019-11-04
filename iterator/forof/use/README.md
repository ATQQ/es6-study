# 16.2 for..of使用

>一个数据结构只要部署了Symbol.iterator属性，就被视为具有 iterator 接口，就可以用for...of循环遍历它的成员。也就是说，for...of循环内部调用的是数据结构的Symbol.iterator方法。

## 数组
```js
let arr=[1,2,3];
for(let v of arr){
    console.log(v);//1 2 3
}
```

## 字符串
```js
let str="abc";
for(let v of str){
    console.log(v);//a b c
}
```

## 与for..in比较

for..in 只能获得对象的键名，不能直接获取键值

for...of循环调用遍历器接口，数组的遍历器接口只返回具有数字索引的属性。这一点跟for...in循环也不一样。

```js
let arr = [1,2,'c','d'];
arr.t='ss';
arr['4']='aa';
for (let i in arr) {
    console.log(arr[i]); // 1 2 c d aa ss
}
for (let v of arr) {
    console.log(v);//1 2 c d aa
}
```
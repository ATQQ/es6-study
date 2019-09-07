# 5.4.3 find()/findIndex() 

>数组实例的find方法，用于找出第一个**符合条件**的数组成员。它的参数是一个回调函数，所有数组成员依次执行该回调函数，直到找出第一个返回值为true的成员，然后返回该成员。如果没有符合条件的成员，则返回undefined。

>数组实例的findIndex方法的用法与find方法非常类似，返回第一个符合条件的数组成员的位置，如果所有成员都不符合条件，则返回-1。

## 查找数组中第一个大于5的成员的值与下标
```js
let arr=[1,3,4,2,8,4,8];
let res=arr.find(v=>{
    return v>5;
})
let resIndex=arr.findIndex(v=>{
    return v>5;
})
console.log(res,resIndex);//8 4
```
## find,findIndex方法的回调有三个参数,依次为当前值,当前的位置,原数组
```js
let res=[1,2,3,4,5].find((v,i,arr)=>{
    return arr[i]===v;
})
console.log(res);//1
```
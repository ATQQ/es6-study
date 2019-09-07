# 5.2 实际运用

## 数组拷贝(普通类型深拷贝,复杂类型浅拷贝)
```js
const arr1 = [1, 2, 3, 4, 5];
const arr2 = [...arr1];
arr2[0] = 666;
console.log('arr2:', arr2);//[666,2,3,4,5]
console.log('arr1:', arr1);//[1,2,3,4,5]
```

## 分割数组(解构赋值)
```js
const arr1=[1,'2','3','4'];
const [,...arr2]=arr1;
console.log('arr2 :', arr2);//arr2 : ["2", "3", "4"]
```

## 合并数组
```js
let arr1=[1,2,3],
arr2=[4,5,6];
let arr3=[...arr1,...arr2];//[1,2,3,4,5,6]
```

## 函数传递参数
```js
function add(x,y) {
    return x+y;
}
const arr=[1,2];
console.log(add(...arr));//3
```

## 字符串转数组
```js
[..."abcdefg"];//[a,b,c,d,e,f,g]
```
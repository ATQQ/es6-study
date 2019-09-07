# 5.4.2 Array.fill

>fill方法使用给定值，填充一个数组。
## 1参数
```js
{
    const arr1 = [1, 2, 3, 4, 5];
    let arr2 = [...arr1].fill(3);
    console.log(arr2);//[3,3,3,3,3]
}
```

## 3参数
```js
{
    const arr1 = [1, 2, 3, 4, 5];
    //用6从下标0开始填充直到下标3之前
    console.log([...arr1].fill(6, 0, 3))//[6,6,6,4,5]
}
```

## 空数组填充仍为空数组
```js
const arr3 = [];
console.log(arr3.fill(0, 0, 10));//[]
```

## 初始化数组
```js
let arr=new Array(5).fill(0);
console.log(arr);//[0,0,0,0,0]
```
# 5.4.1 Array.from

将类数组转换为数组 
1. 带有length属性的
2. 可遍历

## 转换自定义对象
```js
let arrayLike = {
    '0': 'a',
    '1': 'b',
    '2': 'c',
    length: 3
};

// ES5的写法
var arr1 = [].slice.call(arrayLike); // ['a', 'b', 'c']

// ES6的写法
let arr2 = Array.from(arrayLike); // ['a', 'b', 'c']
```

## 字符串转数组
```js
Array.from('hello')//[h,e,l,l,o]
```

## Set转数组
```js
let set=new Set(['name','age']);
console.log(Array.from(set));//["name", "age"]
```

Array.from还可以接受第二个参数，作用类似于数组的map方法，用来对每个元素进行处理，将处理后的值放入返回的数组。
```js
Array.from(arrayLike, x => x * x);
// 等同于
Array.from(arrayLike).map(x => x * x);
```
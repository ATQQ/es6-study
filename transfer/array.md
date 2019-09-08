# 9.1 Array与Set

## Array=>Set
```js
 let arr = [1, 2, 3, 4, 5, 12, 3, 4, 5];
let set = new Set(arr);
console.log(set);
//Set(6) {1, 2, 3, 4, 5, 12}
```

## Set=>Array
```js
let set=new Set();
set.add(1),add({name:'小明'});
let arr1 = Array.from(set);
console.log(arr1);//[1,{name:'小明'}]
```
# 12.2 rest

ES6 引入 rest 参数（形式为...变量名），用于获取函数的多余参数，这样就不需要使用arguments对象了。rest 参数搭配的变量是一个数组，该变量将多余的参数放入数组中。

## 使用arguments
```js
function add() {
    let sum=0;
    let arr = Array.from(arguments);
    for(let v of arr){
        sum+=v;
    }
    console.log(sum);
}
add(1,2,3,4,5);//15
```

## 使用rest
```js
function add(...rest) {
    let sum = 0;
    for (let key of rest) {
        sum += key;
    }
    console.log(sum);
}
add(1,2,3,4,5);//15
```


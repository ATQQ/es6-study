# 3.1 数组的解构

## 只要等号两边的模式相同，左边的变量就会被赋予对应的值。
```js
{
     let a,b,c;
     [a,b,c]=[1,2]
     console.log(a,b,c);// 1 2 undifined
}

{
    let [a,b,c]=[1,,3];
    a,b,c;//1 undefined 3
}

{
    let [a,...b]=[1,2,3];
    a;//1
    b;//[2,3]
}

{
    let [a,b]=[1,[2,3]];
    a;//1
    b;//[2,3]
}

{
    let [a, b, ...c] = [1];
    a;//1
    b;//undefined
    c;//[]
}

{
    let [a,[b],c]=[1,[2,3],4]
    a;//1
    b;//2
    c;//4
}
```

## 设置默认值
```js
let [a='hello']=[];
a;//hello

let [b='world']=['yes'];
b;//yes
```

### ES6 内部使用严格相等运算符（===），判断一个位置是否有值。所以，只有当一个数组成员严格等于undefined，默认值才会生效。
```js
let [c=13]=[undefined];
c;//13

let [d=12]=[null];
d;//null
```

## 实例
* 交换两个变量的值
```js
    let [a, b]=[2,3];
    [a,b]=[b,a];
    console.log(a);//3
```
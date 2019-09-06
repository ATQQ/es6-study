# 1.3.2 块级作用域示例

## 示例1
```js
if(true){
    var a=10;
}
console.log(a);//10
```

## 示例2
```js
if(true){
    let a=10;
}
console.log(a);//error: a is not defined
```

## 示例3
```js
{
    let a=2;
}

{
    let a=3;
    console.log(a);//3
}
```

## 示例4
```js
{
    const a=2;
    console.log(a);//2
    a = 3;//error:"a" is read-only
}
```

## 示例5
```js
{
    const obj={
        name:'小明',
        age:18
    }
    console.log(obj);//{name:"小明",age:18}
    obj.name="小红";
    console.log(obj);//{name:"小红",age:18}
}
```
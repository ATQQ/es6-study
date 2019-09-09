# 12.4 箭头函数

## 声明方式
```js
const arrow = () => {
    console.log('箭头函数')
}
arrow();//箭头函数

//等价于
function arrow(){
    console.log('箭头函数')    
}
```

## 只含一个参数
```js
const oneParam = v => {
    console.log(v);
}
oneParam(666);//666
```

## 如果只有一行返回值
```js
const onlyOneLineReturn = x => x * 2;
console.log(onlyOneLineReturn(3));//6
```

## 多个参数
```js
const moreParam=(a,b,c)=>{
    return {a,b,c};
}
console.log(moreParam(1,2,3))//{a:1,b:2,c:3}
```

## 箭头函数不绑定this
```js
const noBindThis = {
    name: 'apple',
    price: 999,
    num: 100,
    fn() {
        // 本来setTimeout中this指向window
        setTimeout(() => {
            console.log(this.name);
        }, 1000);
    }
}
noBindThis.fn()//apple
```

## 注意点
1. 函数体内的this对象，就是定义时所在的对象，而不是使用时所在的对象。

2. 不可以当作构造函数，也就是说，不可以使用new命令，否则会抛出一个错误。

3. 不可以使用arguments对象，该对象在函数体内不存在。如果要用，可以用 rest 参数代替。

4. 不可以使用yield命令，因此箭头函数不能用作 Generator 函数。

## 不适用地方

### 对象内部的方法调用this
```js
let obj={
    count:0,
    fn:()=>{
        console.log(this);//Window
        this.count++;
    }
}
obj.fn();
```
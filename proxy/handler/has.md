# 10.3 拦截has

## key in obj 时触发
```js
// 被代理的数据
let obj={
    id:18,
    name:'小明',
    age:19
}

let objProxy=new Proxy(obj,{
    has:(target,key)=>{
        if(key in target){
            console.log(`${key}存在`);
            return true;
        }else{
            console.log(`${key}不存在`);
            return false;
        }
    }
})

console.log('id' in objProxy);
// id存在
// true
console.log('abc' in objProxy);
//abc不存在
// false
```
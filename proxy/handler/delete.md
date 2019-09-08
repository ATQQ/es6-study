# 10.4 拦截deleteProperty

```js
// 被代理的数据
let obj={
    id:18,
    name:'小明',
    age:19
}

let objProxy=new Proxy(obj,{
    deleteProperty:(target,key)=>{
        if(key==='id'){
                console.warn("id不能删除");
                return false;
        }
        delete target[key]
        return true;
    }
})

console.log(delete objProxy.id);
//id不能删除
//false
console.log(delete objProxy.age);
//true
```
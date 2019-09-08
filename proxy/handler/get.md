# 10.1 拦截get

```js
//被代理的数据
let account = {
    id: 123,
    name: 'admin',
    phone: '15196520474',
    power:1,
    images:'["name1.jpg","name2.png"]'
}

let accountProxy=new Proxy(account,{
    get:(target,key)=>{
        switch(key){
            case 'power':
                return target[power]===1?'普通用户':'管理员';
            case 'images':
                return JSON.parse(target[key]);
            default:
                return target[key];
        }
    }
})

console.log(accountProxy.images[0]);//name1.jpg
console.log(accountProxy.power);//普通用户
console.log(accountProxy.id);//123
```
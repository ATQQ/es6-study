# 10.2 拦截set

```js
{
    //被代理的数据
    let obj = { name: '小明' };

    let objProxy = new Proxy(obj, {
        set: (target, key, value) => {
            if(key==='sex'){
               if(value===1){
                   return target[key]='女';
               }else{
                   return target[key] ='男';                   
               }
            }
            return target[key]=value;
        }
    })
    objProxy['sex']=1;
    objProxy['age']=1;
    console.log(objProxy);//Proxy {name: "小明", sex: "女", age: 1}
}
```
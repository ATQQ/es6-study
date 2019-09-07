# 6.4.3 Object.keys()/values()/entries()

* Object.keys()返回一个数组，成员是参数对象自身的（不含继承的）所有可遍历属性的键名。
* Object.values()返回一个数组,成员是参数对象自身的所有可遍历属性的键值
* Object.entries()返回一个数组,成员是参数对象自身的所有可遍历属性的键值对

```js
 let obj = {
        name: '小明',
        age: 98
    }

    let keys = Object.keys(obj);
    let values = Object.values(obj);
    let entries = Object.entries(obj);
    console.log('keys :', keys);//["name", "age"]
    console.log('values :', values);// ["小明", 98]
    console.log('entries :', entries);//[["name", "小明"],["age",98]]
```
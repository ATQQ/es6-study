# 8.1 Set的操作方法

## Set本身是一个构造函数，用来生成 Set 数据结构。
```js
let $set=new Set();
```

## Set.prototype.add(value)
```js
let $set=new Set();
$set.add(1);
$set.add('name');
console.log($set);//Set { 1, 'name' }
```

## Set.prototype.has(value)
判断的是值指向的内存地址是否一致
```js
let $set2=new Set();
    $set2.add(1);
    console.log($set2.has(1));// true

    $set2.add({name:'小明'});
    console.log($set2.has({name:'小明'}));//false

    let obj={a:1};
    $set2.add(obj);
    console.log($set2.has(obj));//true
```

## Set prototype.delete(value)
删除Set中的指定值,返回删除是否成功
```js
let $set2=new Set();
    $set2.add(1);
    console.log($set2.delete(1));//true
    console.log($set2);//Set {}
```

## Set.prototype.clear()
清除Set中所有的内容
```js
let $set2=new Set([1,2]);
    console.log($set2);//Set {1,2}
    $set2.clear();
    console.log($set2);//Set {}
```

## keys()/values()/entries()
**set 中key 与value 是同一内容**

* keys():所有键组成的Set Iterator
* values():所有值组成的 Set Iterator
* entries():所有键值对组成的 SetIterator

```js
let $set=new Set(['name','age']);
console.log($set.keys());
//[Set Iterator] { 'name', 'age' }
console.log($set.entries());
//[Set Iterator] { [ 'name', 'name' ], [ 'age', 'age' ] }
console.log($set.values());
//[Set Iterator] { 'name', 'age' }
```
# 7.2 WeekMap

## 含义
WeakMap结构与Map结构类似，也是用于生成键值对的集合。

## 特性
1. 但是它只接受**对象作为键名**,
2. 垃圾回收机制(如果绑定的对象被销毁了,将自动回收)

```js
{
    var $weakMap=new WeakMap();
    $weakMap.set([1,2],3);
    console.log($weakMap);//WeakMap {Array(2) => 3}
}
```
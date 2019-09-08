# 7.1 操作方法

## Map.prototype.set(key,value)
设置键值
```js
let $map1=new Map();
$map1.set([1,2,3],777);
console.log($map1);
//Map { [ 1, 2, 3 ] => 777 }
```

## 定义时初始化
```js
let $map2=new Map([['name','小明'],[[1,2,3],666]]);    
console.log($map2);
// Map { 'name' => '小明', [ 1, 2, 3 ] => 666 }
```

## set支持链式调用
```js
let $map1=new Map();
$map1.set('name','小明').set('age','8');
console.log('$map1 :', $map1);
//$map1 : Map { 'name' => '小明', 'age' => '8' }
```

## Map.prototype.get(key)
取值
```js
let $map1=new Map([['name',"小明"],['ddd',123]]);
console.log('$map1.get("name") :', $map1.get("name"));
console.log('$map1.get("ddd") :', $map1.get("ddd"));
// $map1.get("name") : 小明
// $map1.get("ddd") : 123
```

## Map.prototype.has(key)
查询是否存在
```js
let $map1=new Map([['name',"小明"],['ddd',123]]);
console.log('$map1.has("name") :', $map1.has("name"));
//$map1.has("name") : true
```

## Map.prototype.delete(key)
删除键值
```js
let $map1=new Map([['name',"小明"],['ddd',123]]);
$map1.delete('name');
console.log('$map1 :', $map1);
//$map1 : Map { 'ddd' => 123 }
```

## Map.prototype.keys()
获取map所有键
```js
let $map=new Map([
    ['name','小黑'],
    ['age',18]
])
console.log('$map.keys() :', $map.keys());
//$map.keys() : [Map Iterator] { 'name', 'age' }
```

## Map.prototype.values()
获取所有的值
```js
let $map=new Map([
    ['name','小黑'],
    ['age',18]
])
console.log('$map.values() :', $map.values());
//$map.values() : [Map Iterator] { '小黑', 18 }
```

## Map.prototype.entries()
获取所有的键值对
```js
let $map=new Map([
    ['name','小黑'],
    ['age',18]
])
console.log('$map.entries() :', $map.entries());
//$map.entries() : [Map Iterator] { [ 'name', '小黑' ], ['age', 18 ] }
```

## Map.prototype.clear()
清除所有的键值对数据
```js
let $map=new Map([
    ['name','小黑'],
    ['age',18]
])
$map.clear();
console.log($map);//Map {}
```

## size属性
获取Map成员数目
```js
let $map=new Map([
    ['name','小黑'],
    ['age',18]
]);
console.log($map.size);//2
```
# 9.2 Object与Map

## Object=>Map
```js
let obj={
    name:'小明',
    age:19
}

let map=new Map(Object.entries(obj));

console.log(map);
//Map(2) {"name" => "小明", "age" => 19}
```

## Map=>Object
```js
let map=new Map();
map.set('name','小明').set('age',19);
let obj = Object.fromEntries(map.entries());
console.log(obj);
//{name: "小明", age: 19}
```
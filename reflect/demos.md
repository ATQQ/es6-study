# 11.1 示例

## Reflect.get(target,key);
```js
 let $obj={
        name:'nick',
        age:12,
        sex:'male',
        hobby:'swimming'
    }
console.log(Reflect.get($obj,'name'));//nick
```

## Reflect.set(target,key,value)
```js
 let $obj={
        name:'nick',
        age:12,
        sex:'male',
        hobby:'swimming'
    }
    Reflect.set($obj,'name','sam');
console.log(Reflect.get($obj,'name'));//sams
```

## Reflect.has(target,key)

### 旧写法
```js
let $obj={
        name:'nick',
        age:12,
        sex:'male',
        hobby:'swimming'
    }
console.log('name' in $obj);//true
```

### 新写法
```js
let $obj={
        name:'nick',
        age:12,
        sex:'male',
        hobby:'swimming'
    }
console.log(Reflect.has('name'));//true
```
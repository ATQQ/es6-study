# export

模块功能主要由两个命令构成：export和import。export命令用于规定模块的对外接口
## 简单用法
* demo1
    ```js
    export let a=1;
    export let b=2;
    ```
    对外部输出了2个变量a,b
* demo2
  ```js
  let a=1,b=2;
  export{
      a,
      b
  }
  ```
  此种方式与demo1方式一致

## 输出函数或类
```js
export function add(x, y) {
  return x + y;
};

// 等价于
function add(x,y){
    return x+y;
}
export {
    add
}
```

## as关键字
重命名了函数v1和v2的对外接口。重命名后，v2可以用不同的名字输出两次。
```js
function v1() { return }
function v2() { return }

export {
  v1 as m1,
  v2 as m2,
  v2 as m3
};
```
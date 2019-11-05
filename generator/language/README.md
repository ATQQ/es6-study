# 17.1 语法

## 示例
```js
const say = function* () {
    yield 'a'
    yield 'b'
    yield 'c'
}
const fn = say();
console.log(fn.next());//a
```
## yield

（1）遇到yield表达式，就暂停执行后面的操作，并将紧跟在yield后面的那个表达式的值，作为返回的对象的value属性值。

（2）下一次调用next方法时，再继续往下执行，直到遇到下一个yield表达式。

（3）如果没有再遇到新的yield表达式，就一直运行到函数结束，直到return语句为止，并将return语句后面的表达式的值，作为返回的对象的value属性值。

（4）如果该函数没有return语句，则返回的对象的value属性值为undefined。

### 暂缓执行函数
```js
function* f() {
  console.log('执行')
}

let generator = f();

setTimeout(function () {
  generator.next()
}, 2000);
```

## yield表达式只能用在 Generator 函数里面，用在其他地方都会报错。
```js
const fn=()=>{
    yield "abc"//报错
}
```

## 与 Iterator 接口的关系
>任意一个对象的Symbol.iterator方法，等于该对象的遍历器生成函数，调用该函数会返回该对象的一个遍历器对象。

```js
    let obj={};
    obj[Symbol.iterator]=function*(){
        yield "abc"
        yield 123
        yield "中文"
    }
    console.log([...obj]);//["abc", 123, "中文"]
```

>for...of循环可以自动遍历 Generator 函数运行时生成的Iterator对象，且此时不再需要调用next方法。

```js
function* fn() {
    yield 1;
    yield 2;
    return 6;
  }
  
  for (let v of fn()) {
    console.log(v); // 1 2
  }
```

## next 方法的参数 
yield表达式本身没有返回值，或者说总是返回undefined。next方法可以带一个参数，该参数就会被当作**上一个yield表达式的返回值**。

```js
function* fn() {
    console.log('start');
    console.log(`1. ${yield}`);
    console.log(`2. ${yield}`);
    return 'end';
  }
  
  let genObj = fn();
  genObj.next();
  // start
  genObj.next('a')
  // 1. a
  genObj.next('b')
  // 2. b
```

## next()、throw()、return() 
>next()、throw()、return()这三个方法本质上是同一件事，可以放在一起理解。它们的作用都是让 Generator 函数恢复执行，并且使用不同的语句替换yield表达式。
### next() 将yield表达式替换成一个值。
```js
const g = function* (x) {
    let res = yield x;
    return res;
};
const gen = g(666);
console.log(gen.next());//{value: 666, done: false}
console.log(gen.next(1));//{value: 1, done: true}
```

### throw() 将yield表达式替换成一个throw语句。

```js
const g = function* (x) {
    let res = yield x;
    return res;
};
const gen = g(666);
console.log(gen.next());//{value: 666, done: false}
console.log(gen.throw(new Error("abc")));//Uncaught Error: abc
```

### return() 将yield表达式替换成一个return语句。

```js
const g = function* (x) {
    let res = yield x;
    return res;
};
const gen = g(666);
console.log(gen.next());//{value: 666, done: false}
console.log(gen.return(2));//{value: 2, done: true}
```

## yield* 表达式
如果在 Generator 函数内部，调用另一个 Generator 函数。需要在前者的函数体内部，自己手动完成遍历。
```js
function* f1() {
  yield 'a';
  yield 'b';
}

function* f2() {
  yield '1';
  // 手动遍历 f1()
  for (let v of f1()) {
    console.log(v);
  }
  yield '2';
}

for (let v of f2()){
  console.log(v);
}
//1 a b 2
```

ES6 提供了yield*表达式，作为解决办法，用来在一个 Generator 函数里面执行另一个 Generator 函数。
```js
function* f1() {
  yield 'a';
  yield 'b';
}

function* f2() {
    yield '1';
    yield* f1();
    yield '2';
}

for (let v of f2()){
  console.log(v);
}

//1 a b 2
```

任何数据结构只要有 Iterator 接口，就可以被yield*遍历。
#### 数组
```js
function* f1(){
  yield* ["a", "b", "c"];
}
for(let v of f1()){
    console.log(v);//a b c
}
```

#### 字符串

```js
function* f1(){
  yield* "abc";
}
for(let v of f1()){
    console.log(v);//a b c
}
```

## 作为对象属性的 Generator 函数
```js
let obj={
    * gen(){
        //...code
    }
}

// 等价于
let obj={
    gen:function* (){
        //...code
    }
}
```
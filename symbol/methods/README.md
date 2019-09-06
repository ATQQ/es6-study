# 2.2 方法

## Symbol.for()
有时，我们希望重新使用同一个 Symbol 值，<code>Symbol.for()</code>方法可以做到这一点。它接受一个字符串作为参数，然后搜索有没有以该参数作为名称的 Symbol 值。如果有，就返回这个 Symbol 值，否则就新建并返回一个以该字符串为名称的 Symbol 值。
```js
let a=Symbol.for('fw')
let b=Symbol.for('fw')
console.log(a===b);//true
```

由于Symbol()写法没有登记机制，所以每次调用都会返回一个不同的值。
```js
Symbol("fw") === Symbol("fw")//false
```

## Symbol.keyFor()
<code>Symbol.keyFor()</code>方法返回一个已登记的 Symbol 类型值的key。
```js
let s1 = Symbol.for("fw");
Symbol.keyFor(s1) // "fw"

let s2 = Symbol("sugar");
Symbol.keyFor(s2) // undefined
```


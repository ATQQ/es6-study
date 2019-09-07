# 4.2 模板字符串

## ES5写法
```js
var name='小明',
age=18;
console.log('我叫'+name+'今年'+age+'岁')
```

## ES6 模板字符串写法
```js
var name='小明',
age=18;
console.log(`我叫${name}今年${age}岁`);
```

>注意:模板字符串使用 <code>``</code>,即不是双引号<code>""</code>,也不是单引号<code>''</code>

><code>``</code>通常在键盘左上角<code>ESC</code>按键下方
# 4.3.5 String.padStart()

> ES2017 引入了字符串补全长度的功能。如果某个字符串不够指定长度，会在头部或尾部补全。

## String.padStart(length,fillStr?)头部补全
* length:   补全后的字符串长度
* fillstr:  用于填充的字符串,默认为空格
```js
let str='5678'
console.log(str.padStart(8,'abc'));//abca5678
```
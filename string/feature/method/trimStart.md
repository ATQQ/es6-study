# 4.3.7 String.trimStart()

>ES2019 对字符串实例新增了trimStart()和trimEnd()这两个方法。它们的行为与trim()一致，trimStart()消除字符串头部的空格，trimEnd()消除尾部的空格。它们返回的都是新字符串，不会修改原始字符串。

```js
const s = '  abcd  ';
s.trim() //"abcd"
s.trimStart() //"abc  "
s.trimEnd() //"  abc"
```
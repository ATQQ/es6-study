# 6.4.1 Object.is()

## 描述
ES5中 比较两个值是否相等，只有两个运算符：相等运算符（==）和严格相等运算符（===）。它们都有缺点，前者会自动转换数据类型，后者的NaN不等于自身，以及+0等于-0。
<code>Object.is()</code> 跟===作用相同 区别在于NaN,前者相等,后者不等

```js
console.log(Object.is(NaN,NaN));//true
console.log(NaN===NaN);//false
```
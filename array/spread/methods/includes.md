# 5.4.4 includes()/indexOf()

> Array.prototype.includes方法返回一个布尔值，表示某个数组是否包含给定的值，与字符串的includes方法类似。ES2016 引入了该方法。

```js
[1, 2, 3].includes(2)     // true
[1, 2, 3].includes(4)     // false
```

>该方法的第二个参数表示搜索的起始位置，默认为0。如果第二个参数为负数，则表示倒数的位置，如果这时它大于数组长度（比如第二个参数为-4，但数组长度为3），则会重置为从0开始。

```js
[1, 2, 3].includes(3, 3);  // false
[1, 2, 3].includes(3, -1); // true
```

>在此之前用indexOf判断是否包含目标值,indexOf方法有两个缺点，1.不够语义化，它的含义是找到参数值的第一个出现位置，所以要去比较是否不等于-1，表达起来不够直观。2.它内部使用严格相等运算符（===）进行判断，这会导致对NaN的误判。

```js
[NaN].indexOf(NaN)//-1
[NaN].includes(NaN)//true
```
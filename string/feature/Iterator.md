# 4.1 for of遍历

## ES6 为字符串添加了遍历器接口，使得字符串可以被for...of循环遍历。
```js
const str='abcd';
for(let s of str){
     console.log(s)
}
```
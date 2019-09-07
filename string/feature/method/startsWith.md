# 4.3.2 String.startsWith()

## 判断原字符串是否以目标字符串开头,第二个参数position(可选)默认为0,表示从第几个字符开始向后判断
```js
{
    const str='hello world';
    console.log(str.startsWith('hello'));//true
    console.log(str.startsWith('abc'));//false
    console.log(str,startsWith('hello',1));//false
    console.log(str,startsWith('world',6));//true
}
```
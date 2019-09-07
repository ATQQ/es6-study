# 4.3.3 String.endsWith()

## 判断原字符串是否以目标字符串结尾,同样第二个参数position(可选)默认为原字符串长度,表示从第几个字符开始向前判断
```js
{
    const str='hello world';
  console.log('endsWith', str.endsWith('world'));//true
  console.log('endsWith', str.endsWith('abc'));//false
  console.log('endsWith', str.endsWith('world',11));//true
  console.log('endsWith', str.endsWith('hello', 5));//true
  console.log('endsWith', str.endsWith('hello', 7));//false
}
```
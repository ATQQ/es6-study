# 15.1 基本用法

Promise构造函数接受一个函数作为参数，该函数的两个参数分别是resolve和reject。
* resolve:将Promise对象的状态从"未完成"变为"完成"，在异步操作成功时调用，并将异步操作的结果，作为参数传递出去
* reject:将Promise对象的状态从"未完成"变为"失败",在异步操作失败时调用，并将异步操作报出的错误，作为参数传递出去。

## 模拟ajax
```js
const ajax = () => {
    return new Promise((resolve,reject)=> {
        setTimeout(() => resolve(666),1000)
    })
}

ajax().then((res) => {
    console.log(res);//666
    console.log('任务1');
})
```

## 捕获错误
```js
/**
 * 判断是否为Number
 * @param {Number} num 
 */
function judgeNumber(num) {
    return new Promise((resolve, reject) => {
        if (typeof (num) === 'number') {
            resolve(num);
        } else {
            const err = new Error('不是数字');
            reject(err);
        }
    })
}
judgeNumber('2')
    .then(num => {
        console.log(num);
    })
    .catch(err => {
        console.log(err);//Error: 不是数字
    })
```
## 嵌套示例
```js
const createErr=true;
const ajax = () => {
    return new Promise((resolve, reject) =>{
        setTimeout(() => {
            resolve(111);
        }, 1000)
    })
}

ajax().then((res) => {
    console.log(res);///111
    console.log('任务1');
    return new Promise((resolve,reject)=>{
        setTimeout(() => resolve(222), 1000);
    })
}).then((res)=>{
    console.log(res);///222
    console.log('任务2');
})
```
## finally()
finally方法用于指定不管 Promise 对象最后状态如何，都会执行的操作。该方法是 ES2018 引入标准的。
```js
const promise=new Promise((resolve,reject)=>{...})

promise
.then(result => {···})
.catch(error => {···})
.finally(() => {···});
```
# 15 Promise

## 异步操作示例
### 示例1
```js
 console.log(1);
 setTimeout(() => {
     console.log(2);
 }, 0);
 console.log(3);
 //1 3 2
```
### 示例2
```js
const ajax = cb => {
    setTimeout(() => {
        cb && cb(() => {
            console.log('任务2');
        })
    }, 1000);
}

ajax((cb2) => {
    console.log('任务1');
    setTimeout(() => {
        cb2 && cb2()
    }, 1000);
})
//1s 后:任务1
//2s 后:任务2
```

Promise 是异步编程的一种解决方案，比传统的解决方案——回调函数和事件——更合理和更强大。

所谓Promise，简单说就是一个容器，里面保存着某个未来才会结束的事件（通常是一个异步操作）的结果。

有了Promise对象，就可以将异步操作以同步操作的流程表达出来，避免了层层嵌套的回调函数。此外，Promise对象提供统一的接口，使得控制异步操作更加容易。

Promise也有一些缺点。首先，无法取消Promise，一旦新建它就会立即执行，无法中途取消。其次，如果不设置回调函数，Promise内部抛出的错误，不会反应到外部。第三，当处于pending状态时，无法得知目前进展到哪一个阶段（刚刚开始还是即将完成）。
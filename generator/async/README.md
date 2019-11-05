# 17.2 异步应用
## 模拟轮循
```js
function fn1() {
    return new Promise(resolve => {
        setTimeout(() => {
            console.log('查询中');
            resolve({ code: 0 })
        }, 1000);
    })
}
const getStatus = function* () {
    yield fn1()
}
function autoGetStatus() {
    const gen = getStatus();
    const status = gen.next();
    status.value.then(res => {
        if (res.code === 0) {
            console.log('付款成功');
        } else {
            console.log('暂未付款');
            setTimeout(autoGetStatus(), 500);
        }
    })
}
autoGetStatus();
```

## 异步任务
达不到预期效果的写法
```js
    const ajax = function* () {
        console.log('start');
        yield setTimeout(() => {
            console.log('异步任务结束');
        }, 1000)
        console.log('end');
    }

    const runAjax = ajax();
    runAjax.next();
    runAjax.next();
    //start end 异步任务结束
```

正确写法
```js
    const ajax = function* () {
        console.log('start');
        yield function (cb) {
            setTimeout(() => {
                console.log('异步任务结束');
                cb && cb()
            }, 1000);
        }
        console.log('end');

    }

    const runAjax = ajax();
    const first = runAjax.next();
    first.value(() => {
        runAjax.next();
    })
```


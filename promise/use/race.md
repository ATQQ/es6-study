# 15.3 Promise.race()

Promise.race()方法用于将多个 Promise 实例，包装成一个新的 Promise 实例。

若果有一个实例resolve,Promise.race()就执行resolve,回调值为成功实例的回调内容

只有所有实例都被reject,那么Promise.race()就执行reject,回调内容为所有被reject的实例的错误回调内容组成的数组

## 加载图片示例
复制到浏览器控制台可直接执行预览
```js
let urls = [
        'https://sugarat.top/EasyPicker/admin/assets/i/favicon.png',
        'https://sugarat.top/EasyPicker/admin/assets/i/favicon.png',
        'https://sugarat.top/EasyPicker/admin/assets/i/favicon.png'
    ]

// url做参数生成Promise对象
function getImage(url) {
    return new Promise((resolve, reject) => {
        const img = document.createElement('img');
        img.src = url;
        img.onload = () => resolve(img);
        img.onerror = (err) => reject(err);
    })
}

// 生成所需的Promise对象数组
const $imgs = urls.map(v => {
    return getImage(v);
})
    
// 将准备好的图片插入dom树中
function showRaceImage(img) {
    document.body.appendChild(img);
}

// 执行所有的promise
Promise.race([...$imgs])
    .then(showRaceImage)//成功就插入图片
```
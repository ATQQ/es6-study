# 15.2 Promise.all()

Promise.all方法用于将多个 Promise 实例，包装成一个新的 Promise 实例。

只有所有的实例都resolve,Promise.all才执行resolve,回调值为所有实例的回调内容组成的数组

如果有一个实例被reject,那么Promise.all就执行reject,回调内容为第一个被reject的实例的错误回调内容

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
function showImage(imgs) {
    imgs.forEach(img => {
        document.body.appendChild(img);
    })
}

// 执行所有的promise
Promise.all([...$imgs])
    .then(showImage)//成功就插入所有的图片
```
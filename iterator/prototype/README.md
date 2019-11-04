# 16.3 为不包含iterator的对象扩展

>对于普通的对象，for...of结构不能直接使用，会报错，必须部署了 Iterator 接口后才能使用。但是，这样情况下，for...in循环依然可以用来遍历键名。

```js
let obj = {
  a: 123,
  b: "bbb"
};

for (let k in obj) {
  console.log(k);//a b
}

for (let v of obj) {
  console.log(v);
}
// TypeError: obj[Symbol.iterator] is not a function
```

## 手动实现Object的Iterator
```js
const obj = {
    name: '小明',
    age: 19,
    size: 'small',
    [Symbol.iterator]() {
        let index = 0;
        const values = Object.values(this);
        return {
            next() {
                if (index < values.length) {
                    return {
                        value: values[index++],
                        done: false
                    }
                } else {
                    return {
                        value: undefined,
                        done: true
                    }
                }
            }
        }
    }
}

const fn = obj[Symbol.iterator]();
console.log(fn.next());
console.log(fn.next());
console.log(fn.next());
console.log(fn.next());
for (const key of obj) {
  console.log(key);
}
```

>对于类似数组的对象（存在数值键名和length属性），部署 Iterator 接口，有一个简便方法，就是Symbol.iterator方法直接引用数组的 Iterator 接口。

```js
NodeList.prototype[Symbol.iterator] = Array.prototype[Symbol.iterator];
// 或者
NodeList.prototype[Symbol.iterator] = [][Symbol.iterator];

[...document.querySelectorAll('div')] // 可以执行了
```
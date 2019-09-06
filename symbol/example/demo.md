# 2.4 使用场景

## 旧写法switch
```js
function getArea(shape, options) {
    let area = 0;
    switch (shape) {
        case 'Triangele':
            area = options.w * options.h / 2;
            break;
        case 'Squire':
            area = options.w * options.h;
            break;
            /**more code */
    }
    return area;
}
getArea('Squire',{w:10,h:2});//20
```
## 新写法
```js
const shapeType = {
    Triangle: Symbol(),
    Squire: Symbol()
}
function getArea(shape, options) {
    let area = 0;
    switch (shape) {
        case shapeType.Triangle:
            area = options.w * options.h / 2;
            break;
        case shapeType.Squire:
            area = options.w * options.h;
            break;
        /**more code */
    }
    return area;
}
getArea(shapeType.Squire, { w: 10, h: 2 });
``` 
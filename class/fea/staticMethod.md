# 13.2 静态方法

## 使用示例
使用关键字 static
```js
class Student {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    static sayHello(obj) {
        console.log(obj.name, 'sayHello');
    }
}

let s1 = new Student('小明', 19);
Student.sayHello(s1);//小明 sayHello
```
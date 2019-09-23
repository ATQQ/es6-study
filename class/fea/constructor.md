# 13.1 构造函数

## ES5旧写法
```js
{
    function Student(name, age) {
        this.name = name;
        this.age = age;
    }
    Student.prototype.sayHello = function () {
        console.log(`大家好我叫${this.name},我今年${this.age}岁了`);
    }

    const s1 = new Student('小明', 18);
    console.log('s1 :', s1);
    s1.sayHello();
}
```

## ES6新写法
```js
 class Student {
    /**
     * 构造函数
     * @param {String} name 姓名
     * @param {Number} age 年龄
     */
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    sayHello() {
        console.log(`大家好我叫${this.name},我今年${this.age}岁了`);
    }
}

let s1 = new Student('小明', 13);
s1.sayHello();
```
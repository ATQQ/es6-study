# 13.4 getter与setter
作用跟属性拦截器类似
## getter
```js
 class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    get Name() {
        return this.name + '666';
    }

    get Age() {
        return this.age;
    }
}

let p1 = new Person('小明', 19);
console.log(p1.Name);//小明 666
console.log(p1.Age);//19
```

## setter
```js
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    set Name(value) {
        this.name = value+"--a";
    }

    set Age(v) {
        this.age = v*2;
    }
}

let p1 = new Person('小明', 19);
p1.Age=20;
p1.Name = '小黑';
console.log(p1.Name);//小黑--a
console.log(p1.Age);//40
```
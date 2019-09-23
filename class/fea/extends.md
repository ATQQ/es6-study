# 13.5 继承

## extends关键字
class使用关键字extends 来表示继承

```js
//父类
class Parent {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    baseInfoParent() {
        console.log('name :', this.name);
        console.log('age :', this.age);
    }
}

// 子类
class Child extends Parent {
    // 子类构造函数
    constructor(name, age, id) {
        // 调用父类的构造函数
        super(name, age);
        // 注意:必须先调用super才能使用this
        this.id = id;
    }
    info() {
        this.baseInfoParent();
        console.log('id :', this.id);
    }
}

let child = new Child('小明', 18, 2018313);
child.info();
// name : 小明
// age : 18
// id : 2018313
```

**注意**:在子类构造函数中,必须先调用super才能使用this,否则会报错,ES6 规定，在子类普通方法中通过super调用父类的方法时，方法内部的this指向当前的子类实例。

## super关键字
super 除了即可以当做函数也可以当做对象使用

### 做函数时
只能用来表示父类的构造函数,ES6要求子类的构造函数必须执行一次super
```js
class A {}

class B extends A {
  constructor() {
    super();
  }
}
```
### 做对象时
第二种情况，<code>super</code>作为对象时，在普通方法中，指向父类的原型对象；在静态方法中，指向父类。
```js
class Parent {
  static myMethod(msg) {
    console.log('static', msg);
  }

  myMethod(msg) {
    console.log('instance', msg);
  }
}

class Child extends Parent {
  static myMethod(msg) {
    super.myMethod(msg);
  }

  myMethod(msg) {
    super.myMethod(msg);
  }
}

Child.myMethod(1); // static 1

var child = new Child();
child.myMethod(2); // instance 2
```

在子类普通方法中通过super调用父类的方法时，方法内部的this指向当前的子类实例。
```js
class A {
  constructor() {
    this.x = 1;
  }
  print() {
    console.log(this.x);
  }
}

class B extends A {
  constructor() {
    super();
    this.x = 2;
  }
  m() {
    super.print();
  }
}

let b = new B();
b.m() // 2
```

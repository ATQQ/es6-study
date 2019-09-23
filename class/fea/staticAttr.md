# 13.3 静态属性

## ES6写法
```js
//静态属性
{
    class Teacher {
        constructor(name = '小明', age = 18) {
            this.name = name;
            this.age = age;
            Teacher.count++;
        }
        static showCount() {
            console.log('count :', this.count);
        }
    }
    //静态属性设置
    Teacher.count = 0;

    let t1 = new Teacher();
    let t2 = new Teacher();
    Teacher.showCount();//count:2
}
```

## ES7写法
```js
{
    class Teacher {
        //静态属性定义 
        static count = 0;
        constructor(name = '小明', age = 18) {
            this.name = name;
            this.age = age;
            Teacher.count++;
        }
        static showCount() {
            console.log('count :', this.count);
        }
    }

    let t1 = new Teacher();
    let t2 = new Teacher();
    Teacher.showCount();//count:2
}
```
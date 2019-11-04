# 16 Iterator与for..of

## 1.Iterator(遍历器)

>为所有数据结构，提供了一种统一的访问机制，即for...of循环
 


## 2.for..of

>for...of循环，作为遍历所有数据结构的统一的方法。

>一个数据结构只要部署了Symbol.iterator属性，就被视为具有 iterator 接口，就可以用for...of循环遍历它的成员。也就是说，for...of循环内部调用的是数据结构的Symbol.iterator方法。
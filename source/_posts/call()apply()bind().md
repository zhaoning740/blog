---
title: call apply bind 区别
date: 2018-03-22 16:28:46
tags: call apply bind
---

### 1.call()源码解析 

```bash
function add(c, d) {
  return this.a + this.b + c + d;
}

const obj = { a: 1, b: 2 };

console.error(add.call(obj, 3, 4)); // 10 call改变了this的指向，this指向了ogj
```

实际发生过程可以看成以下这样

```bash 
const obj = {
    a:1,
    b:2,
    add:function(c,d){
        return this.a + this.b + c + d
    }
}
//1 .给obj对象添加一个add属性，这时this就指向了obj
//2. obj.add(5,6)和add.call(obj,5,6)输出结果是一样的
//3. 但是给obj对象添加的属性是没用的，可以用delete删掉
```

### 2. call(),apply(),bind()区别

##### 说在前头：都是用来重定义this的指向的！！



以下例子是没有重定义this指向的：

例1：

```bash
var name = '小王',age = 18;
var obj = {
    name: '小张',
    objAge: this.age,
    myFun:function(){
        console.log(this.name + '年龄' + this.age)
    }
}
console.log(obj.objAge); //18 this指向window
obj.myFun(); //小张年龄undefined
```

 例2：

```bash
var name = 'xiaohong';
function shows(){
    console.log(this.name)
}
shows(); //xiaohong 函数直接圆括号执行this上下文是window
```

##### 2.1 call apply bind 不传参情况下

改变了this指向，bind返回一个新函数，需要圆括号调用

~~~bash
var name = '小王',age = 18;
var obj = {
    name: '小张',
    objAge: this.age,
    myFun:function(){
        console.log(this.name + '年龄' + this.age)
    }
}
var db = {
    name:'红红',
    age:99
}

obj.myFun.call(db); //this指向db 红红年龄99
obj.myFun.apply(db); //this指向db 红红年龄99
obj.myFun.bind(db)(); //this指向db 红红年龄99  

注意：可以发现bind返回的是一个新的函数，需要调用才会被执行
~~~

##### 2.2 call appy bind 传参情况下

~~~bash
var name = '小王',age = 18;
var obj = {
    name: '小张',
    objAge: this.age,
    myFun:function(from,to){
        console.log(this.name + '年龄' + this.age + '来自' + from + '去往' + to)
    }
}
var db = {
    name:'红红',
    age:99
}

obj.myFun.call(db,'成都','上海')； //红红年龄99来自成都去往上海
obj.myFun.apply(db,['成都','上海']); //红红年龄99来自成都去往上海
obj.myFun.bind(db,'成都','上海')(); //红红年龄99来自成都去往上海
obj.myFun.bind(db,['成都','上海'])(); //红红年龄99来自成都，上海去往undefined
~~~

## 总结

1.这三个函数的第一个参数都是this指向的对象。

2.call的第二三个参数是用逗号分隔的。fn.call(obj,'string','string2')

3.apply的第二三个参数是放在一个数组里边传进去的。fn.apply(obj,['string','string2'])

4.bind除了返回的是新函数，需调用以外，参数和call一样。fn.bind(obj,'string','string2')()

5.三者参数不限定，允许是各种类型，包括函数、object等。


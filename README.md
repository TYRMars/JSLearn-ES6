<h1 align="center">ES6，新语法学习。帮助解析框架。</h1>
<p align="center"><img src="http://www.cssxt.com/uploadfile/2017/0705/20170705105116854.jpeg" /></p>

---

<p align="center"><img src="http://www.liuhaihua.cn/wp-content/uploads/2016/02/uuUFNjm.png" /></p>

## 目录
* [01-01](https://github.com/TYRMars/JSLearn-ES6#01-01) `Let、const命令`
* [01-02](https://github.com/TYRMars/JSLearn-ES6#01-02) `解构解析`
* [01-03](https://github.com/TYRMars/JSLearn-ES6#01-03) `正则扩展`

---

## 01-01
### Let、const命令
* 作用域的概念：ES6的块级作用域
* 使用let和const


#### let

```JavaScript
function test() {
  let a = 1; //var a = 1;
  console.log(a);
}
test();
```

* let主要是使用在块级作用域

```JavaScript
function test() {
  for (let i = 0; i < 3; i++) {//一个大括号里，就是一个块作用域
    console.log(i);
  }
  console.log(i); //这里会报错，for循环中就是一个块级作用域
}

test();
```
* ES6强制开启严格模式`use strict`
    * 变量未被声明，会报引用错误❌

```JavaScript
function test() {
  let a = 1;
  let a = 2;
}
test();
```
* let不能重复声明，否则会报错

#### const
```JavaScript
function last() {
  const PI = 3.1415926;
  console.log(PI);
}
last();
```
* const作为常量的定义，常量的含义是无法修改的
    * 如果对PI进行修改PI会报错PI：read-only
    * 声明const必须进行赋值

```JavaScript
function last() {
  const k = {
    a:1
  }
  k.a = 2;
  k.b = 3;
  console.log(k);
}
last();
```
* 当定义对象时（引用类型），`const`定义的对象存储的指针，指针无法改变，但是对象是可以改变的

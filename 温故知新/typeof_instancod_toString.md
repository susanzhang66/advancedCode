<!--
 * @Author: your name
 * @Date: 2020-04-24 14:19:54
 * @LastEditTime: 2020-04-30 15:40:11
 * @LastEditors: your name
 * @Description: In User Settings Edit
 * @FilePath: /vue/Users/rainbow/Documents/工作/前端/learn/高级程序设计/温故知新/typeof_instancod_toString.md
 -->

## **typeof**
```javascript
console.log(typeof 2);               // number
console.log(typeof true);            // boolean
console.log(typeof 'str');           // string
console.log(typeof undefined);       // undefined
console.log(typeof []);              // object 
console.log(typeof {});              // object
console.log(typeof function(){});    // function
console.log(typeof null);            // object

let s = Symbol(); // Symbol函数前不能使用new命令
typeof s  //独一无二的数据。
// "symbol"
```
优点：能够快速区分基本数据类型 缺点：不能将Object、Array和Null区分，都返回object 

## **instanceof** 

```javascript
console.log(2 instanceof Number);                    // false
console.log(true instanceof Boolean);                // false 
console.log('str' instanceof String);                // false  
console.log([] instanceof Array);                    // true
console.log(function(){} instanceof Function);       // true
console.log({} instanceof Object);                   // true

```
优点：能够区分Array、Object和Function，适合用于判断自定义的类实例对象 缺点：Number，Boolean，String基本数据类型不能判断


## Object.prototype.toString.call()
```javascript
var toString = Object.prototype.toString;
 
console.log(toString.call(2));                      //[object Number]
console.log(toString.call(true));                   //[object Boolean]
console.log(toString.call('str'));                  //[object String]
console.log(toString.call([]));                     //[object Array]
console.log(toString.call(function(){}));           //[object Function]
console.log(toString.call({}));                     //[object Object]
console.log(toString.call(undefined));              //[object Undefined]
console.log(toString.call(null));                   //[object Null]

```

优点：精准判断数据类型 缺点：写法繁琐不容易记，推荐进行封装后使用
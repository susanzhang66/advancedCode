<!--
 * @Author: your name
 * @Date: 2020-04-19 15:41:50
 * @LastEditTime: 2020-04-23 17:34:13
 * @LastEditors: your name
 * @Description: In User Settings Edit
 * @FilePath: /vue/Users/rainbow/Documents/工作/前端/learn/高级程序设计/操作符运算/String.md
 -->
String类型。
1.字符字面量 -- 也叫转义字符。

3.转换为字符串。。toString().

第一种方式：
数值、布尔值、对象、字符串值都有toString()方法。
null ,undefined没有 toString()方法。

第二种方式，在不知道类型的情况下，使用String()方法。
String()自动应用上面toString()方法，然后对null,undefined就响应转为字符串。


[].toString() //"";
[1,2,3].toString(); // '1,2,3'
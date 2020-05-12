<!--
 * @Author: your name
 * @Date: 2020-04-18 16:59:45
 * @LastEditTime: 2020-04-19 15:31:34
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /vue/Users/rainbow/Documents/工作/前端/javascript代码/操作符运算/Number类型
 -->
Number 类型
出来十进制表示，整数还可以通过八进制（第一位必须是0）或十六进制表示（前2位必须是0x）。
八进制演进：
```javascript
var num1 = 070   //八进制56.
var num2 = 079    // 无效的八进制， 后面解析为十进制。 79.
var num3 = 08      //无效八进制。 解析为 8.
```
所有八进制，十六进制的数值 进行算术计算时都会转为 十进制计算。
常量：
Number.MAX_VALUE 
Number.MIN_VALUE
-Infinity
Infinity
isFinite();

## 数值转换规则如下：
boolean: 返回1和0.
数字： 返回数值。
null: 返回 0.
undefiend: NaN.
字符串：
  1.只包含数字的直接返回数字。（十进制）
  2.浮点数直接返回浮点数（十进制）
  3.包含十六进制的 “0xf”,则转换为相同大小的十进制。
  4.空字符串 转为 0.
  5.除以上的字符串 转为 NaN.
oject: valueOf(), toString()来转换。

```javascipt
var num1= Number("hello,world")  //NaN
var num2 = Number("")  // 0
var num3 = Number("0000011"); 11
var num4 = Number(true); 1
var num5 = Number(null) // 0
var num6 = Number(undefined) NaN
```
**Number()在转换字符串时比较复杂且不合理。尽量用parseInt()函数。**

**NaN（not a number)**

**parseInt() 最好指定第二个参数以兼容八进制** 

- var num1 = parseInt("1234blue"); // 1234,会忽略字符串前的空字符串，如果是非数字则返回 NaN。
- var num2 = parseInt(""); NaN.
- var num3 = parseInt("oxA")  //10, 十六进制。
- var num4 = parseInt(22.5),  //22 后面识别到 . 这个非数字的所以是22
- var num5 = parseInt("070");  // 56, 八进制。
- var num6 = parseInt("70"); 70  十进制
- var num7 = parseInt(0xf);  //15, 十六进制
- var num8 = parseInt(undefined) // NaN
- var num9 = parseInt(null) // NaN


parseInt("")  NaN.  parseInt(null) // NaN, var num8 = parseInt(undefined) // NaN
Number("") 0 .   Number(null) // 0 , Number(undefined) NaN
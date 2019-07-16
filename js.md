# Js基础

## js 的特点

js不需要像其他环境语言一样，需要一些特定的开发工具和执行环境

浏览器内核 --->渲染引擎 js引擎--->深度 --->国产操作系统

1.简单易用2.解释执行3.基于对象

## js的用途

javascript用来制作web页面交互的效果，提升用户体验

## JavaScript与ECMAscript的关系

ECMAscript是由ECMA也就是前身为欧洲计算机制造商协会，指定的标准。

简单地说ECMAscript不是一门语言，而是一个标准，符合这个标准的比较常见的有:JavaScript

## js的概念

JavaScript是一种轻量级的，基于对象和时间驱动的、跨平台的客户端脚本语言

### 常规概念解释

JavaScript是嵌入到浏览器软件当中去的，只要电脑有浏览器就可以执行js程序代码了。而不像其他语言一样，需要配置语言运行的软件环境，培植起来很麻烦，所以是一种轻量级的，

JavaScript是一种基于对象的程序语言，在程序中，对象事由"属性"和"方法"构成的     并且：js中的对象只要会用就可以了，不需要我们自己去开发对象，是系统制定好的对象

事件驱动：就比如鼠标的点击，一入一出，键盘敲击就是统称为时间，也就是事件来驱动

跨平台：js程序可以再多个平台下运行，如：windows、Linux、mac、IOS.....

客户端脚本程序：js只能在客服短的浏览器来运行，不能在服务器端运行，浏览器是一个翻译器，可以翻译三种代码：html代码、css代码、js代码

### 脚本 ：也就是计算机中的脚本语言是指：依据一定的格式编写的可执行的文件，比如：第一部做什么，第二部做什么、也就是相当于一个大纲

## js的组成

1核心

2.文档对象模型

3.浏览器对象模型

4.ECMAScript定义了这门语言的基础，描述了语言的基本语法和基本对象。

5.DOM描述了处理网页内容的方法和接口

6.BOM描述了与浏览器井陉交互的方法和接口

## 变量

### 1变量的概念：变量是存储信息的容器

### 变量的声明

### 变量的命名规则

变量名可以包含字母，数字，下划线，美元符号

变量名不能以数字开头，可以以字母或者下划线开头

变量名不能使系统的关键字

js中的变量名是区分大小写的

js中变量的名称一定要有意义，也就是语义化

### 多个单词的命名

可以使用驼峰式  也就是每个单词的首字母大写

还有就是下划线进行命名

## 数据类型

### 基本数据类型：

#### 数值型-number

数值型包括：整数和浮点型小数

数值变量：变量的值是数值型的

当其他数据类习惯，转换数值型，赚不过去时，但程序不能报错，这时候就会返回一个nan的值

使用Number()强制转换成数值型

#### 字符型-string

用单引号或者双引号引起来的一个字符串

可以使用String()全局函数，强制转换成字符型

#### 布尔型-Boolean

又称逻辑性

只有两个值

true真

false 假

用于条件判断

可以使用Boolean()全局函数，强制转换成布尔型



#### 未定义类型-undefined

当一个变量未定义，但为赋值时，将返回未定义型，未定义型的值只有一个undefined 的

#### 空型-null

当一个对象不存在时，则返回空，空的值只有一个null



基本数据类型很显著的特点：一个变量名只能存一个值



### 2.复合数据类型或引用数据类型

数组-array

对象-object

函数-function

### 同名变量：下面的变量将替换上面的变量

## 数据类型转换

简单说就是数据类型转换成其他的数据类型，比如，将String类型转换为Number类型，将Number类型转换为Boolean类型

### 数据转换分两种

#### 隐式转换

js会更具运算符自动帮助我们将数据类型转换成能够计算的类型  但是常常会出现一些意外的bug

数值转换不成功则会出现NaN 

string不成功则会出现未定义或者说未赋值

布尔只有两种，错与对

undefined = null



#### 强制转换

强制将数据类型转换成我们想要的类型

##### 例子

console.log(10+"20")//1020

console.log(10-"20")-10

console.log(10-"one")NaN

console.log(10-"101a")NaN

console.log(10*'20')200

console.log(20/'one')NaN

console.log('0' == 0)true

console.log( 0 ==  false)true

console.log ('0'==false)两个都转成数字

### 从字符串中提取整数和浮点函数

#### 1.paeselent()

在一个字符串中，从左到右提取整型，如果遇到非整型的内容，则会停止提取，并返回结果。

#### 2.parseFloat系统函数

在一个字符串中，从左到右提取浮点型，遇到非浮点型，则停止提取，并返回结果。

## 逻辑运算符

逻辑运算符的结果有两个 true 与false 

### &&并且

两个条件都满足才为true 如果有一个条件没有满足 则就是false

### || 或

左右两个条件，只要满足一个就返回true 只有两个都不满足就是false

### ！取反运算

true ！=false 

false ！= true 

取布尔值是真，取反就是假

js中操作符主要包括算术运算符，赋值运算符，比较运算符，逻辑运算符，串符，条件运算符，简单的说就是我们操作的对象或者条件

比如: >/</&&/||

## 流程控制的三大结构

按照程序的书写顺序，一条一条语句执行，不允许跳过任何一条语句

## 三元运算符(三木运算符)

三元运算符也就是三个操作数

### switch---多分支语句

## 循环

### 概念

也就是重复做某一件事，给其特定的条件，如果条件成立，则反复执行某程序段，知道条件不成立为止

### 循环的三要素

 从哪里开始

 到哪里结束

 ### 循环的分类

#### While循环

只要条件成立，就重复不断的执行循环体代码

1.在循环开始前，必须对变量初始化（声明变量，给变量个初始值）；

2.如果while的条件喂true，则会重复不断的执行循环体中的（{}）的代码，如果条件喂false，就退出循环

3.在循环体中，必须要有"变量更新"的语句。换句话说，两次的循环值变量值不能一样，如果一样，则会造成死循环。

#### do-while循环

do-while循环不论条件成不成立，都会执行一次

#### 区别

while是先判断条件，后执行语句

do-while是先执行语句，后判断条件

#### for循环

​	for循环的执行顺序  

1.变量初始化，在循环开始前执行一次，以后永远不在执行了

2.i <= 条件怕断，如果条件喂true ，则重复执行循环体代码；否则，退出循环。你需要循环多少遍，条件就需要进行多少次判断

3.执行循环体代码，循环体代码执行完毕后，程序立即调到"变量更新"模块执行。

4.i++，变量更新，为了避免出现死循环，i++执行完毕后，程序会跳到i<=10条件判断语句，开始第二次循环

跳出本次循环 使用 continue ;

## 函数

### 概念

对于反腐使用的功能代码，对齐封装成一个独立的模块，这种功能代码就是函数

通俗的讲，函数就是一个功能，就是一个方便的工具。

### 特点

函数可以一次定义，也可以多次使用

方便代码管理

便于控制程序的执行时间

函数，可以将常用的功能代码，进行封装。如：用户名的验证、验证码函数、邮箱的验证、手机号码的验证、

### 函数的调用

函数定义是不会执行的，那么，函数必须调用，才会有效果。

### 函数的返回值

return 用于像函数调用者返回一个值，并立刻结束函数的运行。

如果要外部获取到函数内运行的结果，可以通过retuen语句跟后面的要返回的值来实现返回值

### arguments对象

#### 作用

保存所有传定给函数的实参

定义：每个函数内部都有一个叫arguments的东西，是一个伪(类似)数组，可以使用数组里面的一些方法

arguments.length-表示实参的个数

arguments.callee.length表示形参的个数

## Js中函数的事件

### 常用事件

鼠标点击-----onclick

页面或图片加载-----onload

鼠标移入-----onmouseover

鼠标离开-----onmouseout

#### 作用

主要用于和用户之间产生一定的交互，提高页面或程序的交互性

#### 事件与函数关系

当触发事件的时候：执行函数=====按下制冷按钮,空调吹冷风事件-----调用

## 作用域

### 概念

变量在函数内部作用范围内，有函数的地方就有作用域

### 全局作用域和局部作用域

```
全局变量:可以在函数内部和函数外部使用的变量，就是"全局变量"。

在函数外部定义的变量，就是"全局变量"。

"全局变量"即可以在函数外使用，也可以在函数内部使用。

"全局变量"在网页关闭时，自动消失(释放空间)。

总结：在函数外部定义的变量，就是全局作用域


局部变量：只能在函数内部使用的变量，称为"局部变量"。

"局部变量"在函数内部定义，在函数内使用。

"局部变量"在函数外部无法访问。

"局部变量"在函数执行完毕就消失了。

总结：在函数内部定义的变量，就是局部作用域


在函数内部，省略关键字var定义的变量是"全局变量"。

注意：var关键字尽量别省略，省略后"全局变量"和"局部变量"容易搞混淆。

定义变量都使用var
```

### 作用域链

 全局作用域我们称为0级作用域

 定义函数开启的作用域就是1级  -   2级  -  3级 ...以此类推

JavaScript会将这些作用域链接在一起，形成个链条，这个链条就是作用域链 1 - 2  - 3  - 4 ...

### 变量在作用域查找规则

现在当前找，找到就是用当前作用域

如果当前作用域中没有找到，就去上一级作用域中查找

以此类推直到0级位置，如果0级作用域还没有找到，就会报错

### 预解析

#### 概念

浏览器在执行js代码的时候会分成两部分操作：预解析以及逐行执行代码，也就是说连浏览器不会直接执行代码，而是加工处理之后在执行，这个加工处理的过程，我们就称之为预解析



#### 规则

将变量声明和函数声明提升到当前作用于最前面

将剩余代码按着书写顺序依次放到后面

#### 预解析补充

把一个函数赋值给变量(var声明的)，函数声明不会提升

### js的编译和执行

1 先检查语法错误 -- -语法错误，当前代码段不会执行

2   声明提升---  变量提升和函数提升，作用于内所有使用var声明的变量和非匿名函数

3. 开始变异 - - - 逐行执行

   ## 递归

   ### 概念

   如果函数在内部调用他自己，那么这个函数求叫做递归函数

   特点

   1.在函数里面调用自身

   2.要有一个并确定递归结束条件，这个称之为递归出口

   3. 不确定循环执行的次数

## 数组

### 数组的概述

数组的标准定义：数组是可以储存一组或一系列相关数据的容器

数据的理解定义：一数组的集合，称为"数组"；

 ### 数组的索引

数组中有多个值，每个值都有一个编号，可以通过编访问到每个数组中的每个值，数组中的编号就成为下标  或者 索引值

索引值是从0开始

使用数组的目的，就是使用循环遍历数组很方便

### 数组的属性

数组对象属性length，就是指数组中元素的总个数

### 数组的遍历

for   in

### 数组的一些方法

shift 删除数组中的第一个元素，并会将长度减一

pop，删除数组中的最后一个元素，并将长度减一

unshift，往数组前面添加一个  或者 添加多个数组，但是长队也会改变

push，往数组结尾添加一个或多个数组元素，长度也会改变；

concat ， 方法用于连接两个或者多个数组，不会改变原先数组，会返回一个新的数组

reverse   逆向排序，原数组也会被逆向排序

toString  将数组强制转换成字符串

join ("拼接符")  将数组转成字符串  ，中间以拼接符链接

slice(start，end)不会修改原先数组，将原数组中的制定区域数据提取出来。

start 开始   end 结束  如果参数是负值表示从倒数开始，不包含结束位置

splice  删除  用于删除元素，也是两个参数，第一个参数表示要删除第一项的位置，第二个参数表示要删除的项数，也就是从哪里开始，删除到开始位置计算的数组  如果第二个参数为0  则不会删除任何项

sort()方法对数组进行排序

如果a 小于 b  ，排序后的数组  a 在 b 前面面，此时返回一个负数(即上面的return - 1)；

如果a 大于 b ，排序后 a 在 b 后面，则返回一个正数 ，(即上面的 return 1)

如果 a 等于 b ，则返回0；

### 数组的排序

#### 冒泡排序

也就是随便输入几个无序的数字，从开头到结尾比较相邻的两个数字比大小，若大数在前 ，小数在后，则交换两个数字的位置，依次比较，使全部数据按从大到校排序

作用就是按着规律进行排序

#### 选择排序

  将第一位依次与后面的元素相比较，得到最小值，与第一位数字作交换，再用第二位依次与后面元素相比较，得到最小值，与第二位交换。

从原始数据中找到最小元素，并放在数组的最前面。然后在从下面的元素中找到最小元素，放在之前最小元素的后面，知道排序完成

#### 数组去重

也就是会将重复的数组去除掉 ，省略不必要的麻烦

### 堆和栈

我们知道之前学习数据类型时，提过对象，说它是复合数据类型，什么数组，函数都是复合数据类型，它们的最显著特点就是一个变量名可以存多个值。当然对象也是可以存多个值，和数组函数类似的一种东西。

### json 表示对象的使用方法

什么是Json？JSON 指的是 JavaScript 对象表示法（JavaScript Object Notation）

JSON 是轻量级的文本数据交换格式

JSON 独立于语言：JSON 使用 Javascript语法来描述数据对象，但是 JSON 仍然独立于语言和平台。JSON 解析器和 JSON 库支持许多不同的编程语言。 目前非常多的动态（PHP，JSP，.NET）编程语言都支持JSON。

JSON 具有自我描述性，更易理解

## 严格模式

除了正常运行模式，ECMAscript5添加了第二种运行模式：“严格模式”（strict mode）。顾名思义，这种模式是的Javascript在更严格的条件下运行。

2)严格模式的作用：

a.消除了JS语法的一些不合理、不严谨之处，减少一些怪异行为；

b.消除代码运行的一些不安全之处，保证代码运行的安全；

c.提高编译器效率，增加运行速度；

d.为未来新版本的JS做好铺垫

注意点：同样的代码，在“严格模式”中，可能会有不一样的运行结果，一些在“正常模式”下可以正常运行的语句，在“严格模式”下将不能运行，掌握这些内容，有助于更细致深入的理解JS，让你编程一个更好的程序员。

### 严格模式的调用

1、如何进入严格模式？
进入严格模式的标志，书写这一行语句 "use strict"
老的浏览器会把他当成一串普通的字符串，加以忽略

2、“严格模式”有两种调用方式，适用于不同的场合；
针对整个脚本文件：将 "use strict" 放在脚本文件的第一行，则整个脚本文件都将以“严格模式”运行，
如果这行语句不在第一行，则无效，整个脚本以“正常模式”运行。
如果不同模式的代码文件合并成一个文件，这一点需要特别注意。

针对单个函数：将 "use strict" 放在函数的第一行，则整个函数以“严格模式”运行。

脚本文件的变通写法：因为第一种调用方式不利于文件合并，所以更好的做法是，借用第二种方法，将整个脚本文件放在一个立即执行的匿名函数中

### 进入严格模式的变化

进入严格模式之后，需要进行哪些行为变更：

1.全局变量声明时，必须加关键字(var)
正常模式：a = 10;    console.log(a)    //10
严格模式：a = 10;    console.log(a)    //a is not defined

2.this无法指向全局对象
正常模式：function fn(){ console.log(this) }        //window
严格模式：function fn(){ console.log(this) }        //undefined

3.函数内不允许出现重名参数
正常模式：function fn( a,b,b ){ console.log(a,b) }
fn(1,2,3)        //1,3
严格模式：function fn( a,b,b ){ }
//报错：Duplicate parameter name not allowed in this context    在此上下文中不允许出现重复的参数名

4.arguments对象
4.1 arguments对象不允许被动态改变
正常模式：
function fn(a){
    a=20;
    console.log(a);                //20
    console.log(arguments[0]);     //20
}
fn(10);

严格模式：
function fn(a){
    a=20;
    console.log(a);                //20
    console.log(arguments[0]);     //10
}
fn(10);

5、不允许使用arguments.callee

6.新增的保留字：implements，interface，let，package，private，protected，public，static，yield

## ES5新增数组方法

indexOf(data，start)接收两个参数：查找要选择的项(可进行选择)，表示查找起点位置的索引值

forEach()循环  回对数组进行遍历循环，对数组中的每一项运行给定函数。这个方法没有返回值

map(callback)会遍历当前数组，然后调用参数中的方法，返回当前方法的返回值

filter()遍历和过滤

## 字符串

字符串就是一串字符，由双（单）引号括起来。字符串是 JavaScript 的一种基本的数据类型。字符串不能进行算术运算，只能进行“连接”运算。

JS中的任何数据类型都可以当作对象来看。所以string既是基本数据类型，又是对象。

##### 2、字符串的创建

```js
1, 直接使用字符串字面量去创建

   var str1 = “亲, 包邮哦!”;

   alert(typeof str1);

2, 通过new创建字符串对象, 通过new创建的都为object类型

   var str2 = new String(“hello world!”);

   alert(typeof str2);

3, 省略new, 这种方式创建的不是object类型, 而是string类型

   var str3 = String(“hello world”);

   alert(typeof str3);
```

##### 3、**字符串的属性和方法**

```js
1)length：获取字符串的长度。如：var len=strObj.length;

2)toLowerCase():将字符串中的字母转成全小写。如：strObj.toLowerCase();

3)toUpperCase():将字符串中的字母转成全大写。如：strObj.toUpperCase()；

4)charAt(index):返回指定下标位置的一个字符。如果没有找到，则返回空字符串；

```



```js
5)indexOf:返回一个字符串在原始字符串中的索引值(查找顺序从左往右查找)。如果没有找到，则返回-1；

例子：判断用户输入的邮箱地址是否有@符号
var email = prompt("请输入邮箱地址?");
    if(email.indexOf("@")==-1){
   		document.write("邮箱地址" +email+ "不合法");
    }else{
    	document.write("邮箱地址" +email+ "是合法的");
}
```



```js
6)lastIndexOf:在原始字符串中，从右往左查找。如果没有找到，则返回-1；

8)substring()：在原字符串，返回一个字符串；不取结束位置，不能给负值会转成0 

注点意：参数是下标 
```

```js
9)split():将一个字符串切割成若干段，返回一个数组。也就是说将一个字符串转成数组；括号里面可以给空字符串， 会把字符串切割成几份
var res = str.split("");

10)slice():提取字符串的片断，并在新的字符串中返回被提取的部分；不包括结束位置。给负值时，可以返回倒数第几个
var res = str.slice(0, 3);

11）trim()：移除字符串首尾空白；

12）concat()：连接两个或多个字符串，返回连接后的字符串

13)replace()	替换与正则表达式匹配的子串。

14)substr()	从起始索引号提取字符串中指定数目的字符。包含结束位置

15）charAt() 方法可返回指定位置的字符。
```



## Math 和Date

### 什么是对象(Object)

```
人就是一个”对象”,人的特征（属性）有：身高、体重、姓名、性别、年龄。每个人可以有不同的本事(方法)：打游戏、玩打飞机、炒股、开车等都是方法。你们现在只要理解对象是由”属性”和”方法”构成的就行。其实我们学习对象也就是学习它的属性和方法。

JS中对象分类：

JS内置对象：数组对象、日期对象、字符串对象。。。。。等。

BOM对象，浏览器各组件对象，包括：window、document、location、history。。。。

DOM对象，文档对象，包括：所有的HTML标记，每一个HTML标记都是一个对象。

自定义对象，根据自己的项目需要，要自己定义自己的对象。
```

##### 1、对象的创建

```
var obj = {}  //字面量形式

var obj = new Object(); //构造函数形式

```

##### 2、内置对象Math

Math数学对象

Math就是一个静态对象，换句话说：在使用Math对象，不需要创建实例

Math。PI 圆周率

Math。abs   绝对值  如Math。abs(-9)=9;

Math.ceil()向上取整  小数会被去掉 同时会+1

Math。floor  向下取整 (会直接去掉小数)如：Math。floor(9.888) = 9;

Math.round ()四舍五入

Math.pow 求x的y次方。如  Math.pow (2.3) = 8;

Math.sqrt()求平方根 。如 Math.sqrt(121)=11;

toFixed()可以将number数字  四舍五入为指定小数的数字

实例：求直角三角形斜边长

```
function getLong(a, b){
    //定义斜边长的变量
    var c = Math.pow(a, 2) + Math.pow(b, 2);
    //开平方
    c = Math.sqrt(c);
    //输出结果
    console.log(c);
}
getLong(3, 4);
```

实例：网页随机背景

```
//实例：网页随机背景色
var min = 100000;
var max = 999999;
var random = Math.random()*(max-min)+min;
//向下取整
random = Math.floor(random);
document.body.bgColor = "#"+random ;
```

### 内置日期对象Date

日期对象类型使用自 UTC（Coordinated Universal Time，国际协调时间）1970 年 1 月 1 日午夜（零时）开始经过的毫秒数来保存日期。Date 类型保存的日期能够精确到 1970 年 1 月 1 日或之后的 285616 年。

#### 简单模式get

getFullYear()获取年

getMonth()获取月份 这里月份是从0开始  要+1

getDate()获取日

getDay()获取周

getHours()获取小时

getMinutes()获取分钟

getSeconds()获取秒数

getMilliseconds()获取毫秒

#### 时间戳

d.getTime（）

获取从1970年1月1日到现在的毫秒

d也就是返回本地的时间

```
1.粗野模式，简单粗暴，但是会清零时分秒
var d = new Date("2008/8/8");

2.复杂模式
var d = new Date();
d.setFullYear(2009);    //设置年
d.setMonth(6);          //设置月，超过11，累加年
d.setDate(27);          //设置日，超过最大日期，累加月

d.setHours(40);         //设置小时，超过24，累加天
d.setMinutes(40);       //设置分钟，超过60，累加小时
d.setSeconds(40);       //设置秒，超过60，累加分钟
d.setMilliseconds(40);  //设置毫秒，超过1000，累加秒

d.setTime(10000)        //设置从1970年1月1日过去了多少毫秒

console.log(d)          //返回更改后的年月日 时分秒

注意set系列的返回值
console.log(d.setFullYear(2009));
//返回从1970年1月1日，到当前设置的时间的毫秒数

```

```

```



##### 4、定时器 - 延时器



```

```









```
延时器方法—setTimout()

功能：设置一个延时器，换句话说：时间一到，就执行JS代码一次。

语法：var timer=window.setTimeout(code,millisec)

参数：

code：是任何合法的JS代码，一般情况下是JS函数，该函数要放在引号中。

举例：window.setTimeout(“close()”,2000);

举例：window.setTimeout(init,2000);//传函数地址，因此不需要加括号。如果加括号，是将函数的执行结果传到方法中。

millisec:毫秒值。1秒=1000毫秒。

返回值：返回一个延时器的id变量，这个id变量给clearTimeout()用来清除。

clearTimeout()

功能：清除延时器id变量。

语法：window.clearTimeout(timer)

参数：timer就是由setTimeout()设置的延时器的id变量。

```



##### 5、定时器



```

```









```
setIerval()

功能：设置一个定时器。定时器，重复不断的执行JS代码(周期性)。

语法：var timer=window.setIerval(code,millisec)

参数：

code：是任何合法的JS代码，一般情况下是JS函数，该函数要放在引号中。

举例：window.setIerval(“close()”,2000);

举例：window.setIerval(init,2000);//传函数地址，因此不需要加括号。如果加括号，是将函数的执行结果传到方法中。

millisec:毫秒值。1秒=1000毫秒。

返回值：返回一个延时器的id变量，这个id变量给clearIerval()用来清除。

clearIerval()

功能：清除延时器id变量。

语法：window.clearIerval(timer)

参数：timer就是由setIerval()设置的延时器的id变量。

```

| 日期（毫秒）转成天数、时、分、秒公式 |                                                              |      |      |      |
| ------------------------------------ | ------------------------------------------------------------ | ---- | ---- | ---- |
| 毫秒数                               | 总秒数：seconds(秒) = parseInt((用将来的时间毫秒 - 现在的时间毫秒)/1000)); |      |      |      |
| 天数                                 | d = parseInt(seconds/3600/24);                               |      |      |      |
| 小时                                 | h = parseInt(seconds/3600%24);                               |      |      |      |
| 分钟                                 | m = parseInt(seconds/60%60);                                 |      |      |      |
| 秒                                   | s = parseInt(seconds%60);                                    |      |      |      |
|                                      |                                                              |      |      |      |

## Bom

#### 一、BOM介绍：

1、BOM（ Browser Object Model）---> 浏览器对象模型。

2、BOM 作用：主要提供了访问和操作浏览器各组件的方式。

window浏览器窗口对象是js中最大的对象。其他所有的对象，都是window的子对象

document文档对象，代表一个网页

location地址栏对象，对地址栏的操作一些方法

Navigatior浏览器软件对象，主要用来判断用户用的是什么浏览器，可以解决兼容性问题

screen屏幕对象，可以获取屏幕相关的信息

history历史记录对象，可以对浏览器的历史记录进行相关的操作

```
、window是全局浏览器内置顶级对象 表示浏览器中打开的窗口（没有应用于window对象的公开标准，不过所有浏览器都支持该对象）Window 对象表示一个浏览器窗口或一个框架。

2、在客户端 JavaScript 中，Window 对象是全局对象，所有的表达式都在当前的环境中计算。也就是说，要引用当前窗口根本不需要特殊的语法，可以把那个窗口的属性作为全局变量来使用。

例如，可以只写 document，而不必写 window.document。

同样，可以把当前窗口对象的方法当作函数来使用，如只写 alert()，而不必写 Window.alert()。

除了上面列出的属性和方法，Window 对象还实现了核心 JavaScript 所定义的所有全局属性和方法。
```

#### 三、location地址栏对象

```
1、hostname 设置或返回当前URL的主机名

2、href：获取地址栏中完整的地址。可以实现JS的网页跳转。location.href = “http://www.sina.com.cn”;

3、pathname：文件路径及文件名

4、protocol：协议，如：http://、ftp://

5、hash：锚点名称。如：#top

6、reload([true])：刷新网页。true参数表示强制刷新

7、注意：所有的属性，重新赋值后，网页将自动刷新。

<meta  http-equiv = “refresh”  content = “5;url=http://www.sina.com.cn” />
```



####  四、navigator对象

```
1、appName：浏览器软件名称   appCodeName

2、appVersion：浏览器软件的核心版本号。

3、platform：平台

4、userAgent浏览器版本信息
```

#### 五、history对象

```
1、back（）  后退

2、forward（） 前进

3、go（） 

4、history.back（）===  history.go（-1） 浏览器中的  后退

5、history.forward() === history.go  ( 1 )   浏览器中的  前进 
```

#### 六、screen屏幕对象

```
1、Width：浏览器屏幕的宽度，只读属性。  window.screen.width 

2、Height：浏览器屏幕的高度，只读属性。 window.screen.height

3、availWidth：屏幕的有效宽度，不含任务栏。只读属性。

4、availHeight：屏幕的有效高度，不含任务栏。只读属性。
```

#### 七、window对象事件

```
1、window.onload 当网页加载完成，指<body>标记的所有内容全部加载完成，才触发该事件(条件)

2、为窗口添加滚动条事件

onscroll 滚动事件

 scrolltop 垂直滚动条滚动的距离
 scrollleft 水平滚动条滚动的距离
 
 window.innerHeight - 浏览器窗口的可见高度 
 window.innerWidth - 浏览器窗口的可见宽度 

兼容写法：var scrolltop = document.documentElement.scrollTop||document.body.scrollTop; 

3、window.onresize 事件会在窗口或框架被调整大小时发生
```

## DOM

#### 一、DOM对象介绍

1、DOM Document Object Model ，文档对象模型。我们可以把网页中的所有“东西”看成是“对象”。

2、DOM是W3C制定的网页标准或规则，而这个标准，在浏览器中，以“对象”的形式得以实现。

3、DOM的官方定义：DOM可以使脚本，动态的访问或操作，网页的内容、网页外观、网页结构。

#### 二、DOM的分类

1、核心DOM：提供了同时操作HTML文档和XML文档的公共的属性和方法。

2、HTML DOM：针对HTML文档提供的专用的属性方法。

3、XML DOM：针对XML文档提供的专用的属性和方法。(了解)

4、CSS DOM：提供了操作CSS的属性和方法。

5、Event DOM：事件对象模型。如：onclick、 onload等。

#### 四、核心DOM的操作

1、认识DOM中元素节点类型

```
document文档节点，代表整个网页，不代表任何HTML标记。但它是html节点的父节点

element元素节点，指任何HTML标记。每一个HTML标记就称一个“元素节点”。它可以有文本节点和属性节点

attribute属性节点。指HTML标记的属性

text节点。是节点树的最底节点
```

2、DOM中访问节点

```
firstChild：第1个子节点

lastChild：最后1个子节点

childNodes：子节点列表，是一个数组  childNodes[0]

parentNode：父节点

nodeName：节点名称  返回标签名

nodeValue 属性节点的的属性值

nodeType 节点类型，返回值是数字  

如果节点是元素节点，则 nodeType 属性将返回 1。如果节点是属性节点，则 nodeType 属性将返回 2。返回3是文本节点



查找<html>标记的方法

document.documentElement

查找<body>标记的方法

document.body

```

3、对节点的属性操作

```
setAttribute(name,value)：给某个节点添加一个属性

getAttributeNode(name)：获取某个节点属性的值

removeAttribute(name)：删除某个节点的属性
```

4、创建节点

```
document.createElement(tagName)：创建一个指定的HTML标记，一个节点

tagName：是指不带尖括号的HTML标记名称  

举例：var imgObj = document.createElement(“img”)


parentNode.appendChild(childNode)：将创建的节点，追加到某个父节点下。

parentNode代表父节点，父节点必须存在。

childNode代表子节点。

举例：document.body.appendChild(imgObj)

box.nsertBefore() 方法可在已有的子节点前插入一个新的子节点 先放要排在前面的元素， 再写其他元素
```

5、删除节点

```
parentNode.removeChild(childNode)：删除某个父节点下的子节点。

parentNode代表父节点。

childNode代表要删除的子节点。

举例：document.body.removeChild(imgObj)

remove()直接删除当前项
```

#### 五、HTML DOM的操作

核心DOM中，提供的属性和方法，已经可以操作网页了。为什么还要有HTMLDOM呢？

如果在核心DOM中，网页中节点层级很深时，访问这个节点时将十分麻烦。

那么，HTMLDOM中就提供了通过id直接找节点的方法，而不用再HTML根节点开始。

```
1、getElementById()

功能：查找网页中指定id的元素对象。

语法：var obj = document.getElementById(id)



2、getElementsByTagName(tagName)

功能：查找指定的HTML标记，返回一个数组

语法：var arrObj = parentNode.getElementsByTagName(tagName)

参数：tagName是要查找的标记名称，不带尖括号。

返回值：返回一个数组。如果只有一个节点，也返回一个数组。


3、 getElementsByName("Name")

功能：通过name值获取元素，返回值是数组，通常用来获取有name的input的值

4.getElementsByClassName()  

功能：通过class名获取元素，返回值是数组

ES5新增选择器：

5.document.querySelectorAll();    //强大到超乎想象，支持IE8+。ECMAScript借鉴了jQuery选择器的

6.document.querySelector();  返回单个元素
```

#### 六、元素属性的对象：

a、在HTML中叫“标记” b、 在DOM中叫“节点” c、在JS中叫“对象”

```
tagName：标签名称，与核心DOM中nodeName一样

className：CSS类的样式

id：同HTML标记id属性一样

title：同HTML标记的title属性一样

style：同HTML标记的style属性一样

innerHTML：包含HTML标记中的所有的内容，包括HTML标记等
```

#### 七、CSS DOM动态样式

```
使用JS操作CSS中的各种属性。JS只能操作或修改行内样式，对于类样式，通过className来赋值。

如：imgObj.className=”imgClass”;

1、style对象

每个HTML标记，都有一个style属性。但这个style属性又是一个style对象。

那么，这个style对象属性有哪些？style对象的属性，与CSS中的属性，一一对应。

因此，style对象用来代替CSS。

如：imgObj.style.border=”1px solid red”;

2、style对象属性与CSS属性的转换

(1)、如果是一个单词，style对象属性，与CSS属性一样。

(2)、如果是多个单词，第一个单词全小写，后面每个单词首字母大写，并去掉中划线。
```
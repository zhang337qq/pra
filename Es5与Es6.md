### ES5和ES6

------

#### 一、ES5严格模式

除了正常运行模式，ECMAscript 5 添加了第二种运行模式："严格模式"（strict mode）。顾名思义，这种模式使得Javascript在更严格的条件下运行。

##### 1、严格模式的特点



```
a、消除Javascript语法的一些不合理、不严谨之处，减少一些怪异行为;

b、消除代码运行的一些不安全之处，保证代码运行的安全；

c、提高编译器效率，增加运行速度；

d、为未来新版本的Javascript做好铺垫。

"严格模式"体现了Javascript更合理、更安全、更严谨的发展方向，包括IE 10在内的主流浏览器，都已经支持它

另一方面，同样的代码，在"严格模式"中，可能会有不一样的运行结果；一些在"正常模式"下可以运行的语句，在"严格模式"下将不能运行。掌握这些内容，有助于更细致深入地理解Javascript，让你变成一个更好的程序员。
```



##### 2、进入严格模式 "use strict"



```

```









```
<script>
    
    "use strict"

    console.log("已经进入严格模式");

</script> 
```



##### 3、严格模式时注意事项



```

```









```
a、全局变量声明时 必须加var

b、this 无法指向全局对象

c、函数内重名属性 - 在函数上下文中不允许重复的参数名称


d、arguments对象

arguments对象不允许被动态改变

arguments对象不允许被自调用


e、新增保留字； implements, interface, let, package, private, protected, public, static, yield
 
```



 

#### 二、ES5新增常见方法

##### 1、数组



```

```









```
2个索引方法：indexOf() 和 lastIndexOf()；

5个迭代方法：forEach()、map()、filter()、some()、every()；

some(): 方法用于检测数组中的元素是否满足指定条件（函数提供）。如果有一个元素满足条件，则表达式返回true , 剩余的元素不会再执行检测。否则返回false

every(): 方法用于检测数组所有元素是否都符合指定条件（通过函数提供）。如果有一个不符合就返回false


2个归并方法：reduce()、reduceRight()；

reduce() 方法接收一个函数作为累加器，数组中的每个值（从左到右）开始缩减，最终计算为一个值。

reduceRight() 方法的功能和 reduce() 功能是一样的，不同的是 reduceRight() 从数组的末尾向前将数组中的数组项做累加。
```



 

##### 2、字符串



```

```









```
trim();// 去掉字符串前后空格
trimLeft()
trimRight()


反序列化
var str = '{"name" : "张三"}';

JSON.parse(str); 用于从一个字符串中解析出json对象

注意点：单引号写在{}外，每个属性名都必须用双引号，否则会抛出异常。



序列化
var obj = {a:1, b:2};

JSON.stringify(); 用于从一个对象解析出字符串

日期对象得到当前日期的毫秒数
Date.now();  
```



 

#### 三、ES6

##### 1、let方法

块级作用域 一种普遍存在于各个语言中的作用域范围；



```

```









```
{
    var a = 10;
    let b = 20;
}

console.log(a)//10
console.log(b)// a is not defined
```



我们可以发现，在一个大括号中用let声明的变量在外部不可访问了，每个大括号都是独立的作用域



```

```









```
for(var  i = 0 ; i < aLi.length ; i ++){
    aLi[i].onclick = function(){
    console.log(i);  //永远都是aLi.length
    }
}

for(let i = 0 ; i < aLi.length ; i ++){
    aLi[i].onclick = function(){
        console.log(i);// 对应下标
    }
}
```



有了let声明我们在函数外部就无法访问到 i ，i作为下标只存在于for循环中， 所以，这个时候每个i都是独立的；我们在点击的时候可以轻易的获取当前元素的下标，而不用做很多繁琐的处理了

 

之前有提到过，JS中var声明一个变量是存在声明提升的，这是JS中的一个缺陷所在， **但是现在的let不存在声明提升**；



```

```









```
console.log(a); //undefined;

var a = 10;

console.log(b)//b is not defined;

let b = 10;
```



暂时性死区

```
var a = 10;

    if(true){

    console.log(a);//ReferenceError(引用错误): a is not defined;
    let a = 20;

}
```

ES6规定在某个区块中， 一旦用let或const声明一个变量，那么这个区块就变成块级作用域，用let 或者const声明的变量即为该区块绑定， 该变量不受任何变量影响。 在该变量使用let声明前不可以用。在语法上，我们叫这种情况为：暂时性死区 (temporal dead zone，简称 TDZ)

 

##### 2、const方法

const声明的是一个常量

```
const a = 20;

a = 30;    //Uncaught TypeError: Assignment to constant variable.
```

 

 

##### 3、字符串扩展

字符串的 Unicode 表示

```
Unicode编码可以保存世界上所有的符号  使用两个四位的十六进制保存中文， 一个表示不了

字符串的 Unicode 表示;  规则为\u + 四位十六进制;

例如: console.log("\u0061");

打印结果是 a；


这种新的字符表示方式只能表示  \u 0000 ~ \u ffff 之间的数字。 如果超出范围必须用双字节表示;

console.log("\uD842\uDFB6"); 

打印结果是 𠮶

如果不按照规则熟悉书写 例如 console.log("\uD842\uDFB69") 


这个9是多余字符； 那么则认为这段字符是 \uD842\uDFB6 + 9 所以打印结果是 𠮶9；

如果想要一次性表示超出范围的字符那么我们可以使用{}来表示；

例如:

console.log("\u20BB9");  这个的打印结果是 拆分开来的 ₻9

console.log("\u{20BB9}"); 这个打印的结果是一个完整的字符

ES6支持多种格式的字符表示;
```

 

字符串的新增方法

```
1、repeat()重复功能

'x'.repeat(3)  //xxx；

重复字符串;


2、includes()  startsWith() endsWith()  判定字符串中是否存在某个字符串;

var s = 'Hello world!';

s.startsWith('Hello') // true      以参数开头
s.endsWith('!') // true            以参数结尾
s.includes('o') // true            包括参数;

第二种方法接受第二个参数，第二个参数表示从第几位开始;

var s = 'Hello world!';

s.startsWith('world', 6) // true
s.endsWith('Hello', 5) // true
s.includes('Hello', 6) // false


3、for of 

一种新的遍历方式;

for of 可以用于遍历字符串：

var s = "abc";

for(let  b of s){

	console.log(b) // "a"  "b"  "c"

}
```

 

字符串模板

```
ES6中存在一种新的字符串， 这种字符串是 以 ` `  (波浪线上的那个字符 > 反引号)括起来表示的；

通常我们想要拼接一个带有标签的字符串， 是用这样的方式:

bianliang + " <strong>这是一个文字" + obj.name + "</strong> " + bianliang

红色为变量;

但是有了ES6字符串一切都变得非常简单了;

`  ${bianliang} <strong>这是一个文字${obj.name}</strong>${bianliang} `

用 ${ } 扩住变量让拼接变得非常容易;

非常简单的换行；

`In JavaScript \n is a line-feed.`     
```

##### 

##### 4、=>箭头函数

```
先看区别吧，原来的写法
 
var test = function(x){
    return x+2;
}

使用箭头函数： var test = (x) =>x+2;

var  函数名 = 参数 => 运算规则;

看起很简单吧？

省略了function、return关键字和大括号。

使用方法跟以前一样没区别 test(5); 
```

还有好处就是，自动绑定this

```
var obj = {    

    left : 200,    

    move : function(){         

        setTimeout(function(){            

            //this.left = 100;              

            //以前这里不能写this，这的this指window      

        },1000);  
    }
}
```

使用了箭头函数

```
var obj = {    

    left : 200,    

    move : function(){         

        setTimeout( ()=>{          

            this.left = 100;      

        },1000);    

    } }
```

箭头函数this指向的固定化，并不是因为箭头函数内部有绑定this的机制，实际原因是箭头函数根本没有自己的this,导致内部的this就是外层代码块的this。正是因为这个，所以箭头函数也不能做构造函数。

 

##### 5、解构赋值

基本

```
var [a,b,c] = [1,2,3];
// a = 1
// b = 2
// c = 3
```

可嵌套

```
let [a, [[b], c]] = [1, [[2], 3]];
// a = 1
// b = 2
// c = 3
```

可忽略

```
let [a, , b] = [1, 2, 3];
// a = 1
// b = 3
```

不完全解构

```
let [a = 1, b] = [];
// a = 1, b = undefined
```

字符串等

```
let [a, b, c, d, e] = 'hello';
// a = 'h'
// b = 'e'
// c = 'l'
// d = 'l'
// e = 'o'
```

 

应用：交换两个变量的值

```
var a = 10;
var b = 20;

console.log(a, b);

[b, a] = [10, 20];
console.log(a, b);
```

 

##### 6、 Symbol类型

ES5中包含5种原始类型：string、number、boolean、null和undefined。ES6引入了第6种原始类型——Symbol

ES5的对象属性名都是字符串，很容易造成属性名冲突。比如，使用了一个他人提供的对象，想为这个对象添加新的方法，新方法的名字就有可能与现有方法产生冲突。如果有一种机制，保证每个属性的名字都是独一无二的，这样就从根本上防止了属性名冲突。这就是ES6引入`Symbol`的原因。

Symbol 值通过`Symbol`函数生成。这就是说，对象的属性名可以有两种类型：一种是字符串，另一种是Symbol类型。凡是属性名属于 Symbol 类型，就都是独一无二的，可以保证不会与其他属性名产生冲突。

注意点： symbol不能使用new去构造， 因为symbol是一个基本数据类型

```
var obj = {};
// obj.name = "张三";
// obj.name = "老王";

obj[Symbol("name")] = "张三";
obj[Symbol("name")] = "老王";
console.log(obj);
```

 

##### 7、Set

Set是新的数据结构。它类似于数组，但是成员的值都是唯一的，没有重复的值。是一个值的集合

注意点：Set里面的值是唯一的，不能有重复的

```
var s = new Set(["张三", "李四", "王五"]);
```

属性：

`size`：返回值的长度

方法

- `add(value)`：添加一个值，返回Set结构本身
- `delete(value)`：删除某个值，返回布尔值
- `has(value)`：返回布尔值，表示是否是成员
- `clear()`：清除所有成员，无返回值

可以用于数组去重

```
var arr = [1, 2, 6, 2, 6];
var s = new Set(arr);
//把类数组对象转成数组返回
var newArr = Array.from(s);
console.log(newArr);
```

 

##### 8、Map对象

**Map**对象保存键/值对，是键/值对的集合。任何值(对象或者原始值) 都可以作为一个键或一个值。Map结构提供了值与值的对象， 是一种更完善的hash（哈希）结构。它类似对象也是键值对的集合，但是键的范围不限于字符串，各种类型都可以当做键。

**注意点**：对象不能把其他类型当做键

```
var obj1 = {"a" : 1};
var obj2 = {"b" : 2};

var obj = {};
//在内部无论你传什么值进来,都会自动给你转成字符串
obj[obj1] = "hello";
obj[obj2] = "world";

console.log(obj);

console.log(typeof obj[obj1]); //string
```

 

Map方式创建

```
var obj1 = {"a" : 1};
var obj2 = {"b" : 2};

//通过构造函数
var map = new Map([
    ["name", "张三"],
    ["age", 18],
    ["sex", "男"],
    [obj1, "hello"],
    [obj2, "hello"],
    [[1, 2], "我是数组"]
]);
console.log(map);
```

 

属性:

`size`：返回值的长度

`keys()` : 取出Map里面所有的键

`values()` : 取出Map里面所有的值

`entries()` ：取出里面所有的键和值

 

方法:

`set()` : 增加、修改

`get()`: 获取

`has()`: 判断里面有没有这个值 true / false

`delete()` : 删除

`clear()` : 清除

 

##### 9、数组方法:Array.from

Array.from()方法就是将一个类数组对象或者可遍历对象转换成一个真正的数组。

```
var str = "abc";
console.log(str);

//返回一个数组
var arr = Array.from(str);
console.log(arr);
```

 


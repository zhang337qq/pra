### this指向

------

#### 一、认识this



```

```









```
1、核心一句话 - 哪个对象调用函数，函数里面的this指向哪个对象。

2、浏览器解析器在调用函数时每次都会向函数内部传递一个隐含的参数，这个隐含的参数就是this,this指向的是一个对象，这个对象我们称之为函数执行的上下文对象。

3、根据函数的调用方式的不同，this会指向不同的对象，这也是this的存在的意义所在。
```



 

每个函数都有自己的执行环境，也叫执行上下文（Execution Context） 函数里面的this是谁？

- 函数调用圆括号时，函数的this是window对象

- 函数作为一个对象的方法，对象打点调用，函数的this就是这个对象

- 函数是事件处理函数时，函数的this就是触发这个this的对象

- 定时器调用函数时，this是window对象

  

  ```
  
  ```

  

  

  

  

  ```
  function demo(){
  ```

  ```
      console.log(this);
  ```

  ```
      console.log(this.a);
  ```

  ```
  }
  ```

  ```
  var a = 10;
  ```

  ```
  setInterval(demo, 1000);
  ```

  

   

- 数组中存放的函数，被数组索引之后加圆括号调用，this就是这个数组

  

  ```
  
  ```

  

  

  

  

  ```
  //在数组中
  ```

  ```
  function demo(){
  ```

  ```
      console.log(this);
  ```

  ```
      console.log(this === arr);
  ```

  ```
  }
  ```

  ```
  var arr = [demo, "张三", 10];
  ```

  ```
  arr[0]();
  ```

  

 

#### 二、备份this

在定时器外面的事件处理函数中，this就是事件元素，我们可以把this进行备份使用来使用，因为在定时器里面this指向的是window对象。



```

```









```
box.onclick = function(){
    console.log(this);
    var that = this;
    setInterval(function(){
        //this执行window
        that.style.background = "red";
    },2000)
}
```



 

#### 三、bind、call、apply方法

**1、this是什么？谁调用当前函数或者方法，this就是谁。**

**2、bind、call、apply方法可以改变当前this的指向。**

 

bind()方法：修改函数或方法中的this为指定的对象，并且会返回一个修改后的之后的新的函数给我们。

注意点：bind()方法除了修改this以外，还可以传递参数，只不过参数必须写在this对象的后面



```

```





```
var obj = {
    name : "小何"
}
function test(a, b){
```





```
    console.log(this);
    console.log(a, b);
}
var fn = test.bind(obj, 10, 20);
fn();
```



 

call()方法: 修改函数或方法中的this为指定的对象，并且会立即调用修改之后的函数。

注意点：call()方法除了可以修改this以外，还可以传递参数，只不过参数必须写在this对象的后面



```

```









```
var obj = {
    name : "小刘"
}
function test(a, b){
    console.log(this);
    console.log(a, b);
}
var fn = test.call(obj, 5, 10);
```



apply()方法: 修改函数或方法中的this为指定的对象，并且会立即调用修改之后的函数。

注意点：注意点：call()方法除了可以修改this以外，还可以传递参数，只不过参数必须通过数组的方式传递



```

```









```
var obj = {
    name : "小何"
}
function test(a, b){
    console.log(this);
    console.log(a, b);
}
var fn = test.apply(obj, [10, 5]);
```



修改方法中的this指向



```

```









```
var obj = {
    name : "小何"
}

function Person(name, age){
    this.name = name;
    this.age = age;
    this.say = function(){
        console.log(this.name);
    }
}
//修改方法中的this指向
var p1 = new Person("小明", 18);
p1.say();

var fn = p1.say.bind(obj);
fn();
```



 


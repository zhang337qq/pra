## PHP

服务 后台

应用程序分类：

B/S：Browser（浏览器）/ Server（服务器）

C/S：Client（客户端）/ Server（服务器）

http协议：基于TCP/IP的无状态通信协议

前端（浏览器客户端）向后台（web服务器端）发送http请求获取数据



**http请求报文：**

一个HTTP请求报文由请求行（request line）、请求头部（header）、空行和请求数据4个部分组成

form的enctype属性为编码方式，常用有两种：application/x-www-form-urlencoded和multipart/form-data，默认为application/x-www-form-urlencoded。

当action为get时候，浏览器用x-www-form-urlencoded的编码方式把form数据转换成一个字串（name1=value1&name2=value2...），然后把这个字串追加到url后面，用?分割，加载这个新的url。

当action为post时候，浏览器把form数据封装到http body中，然后发送到server。 如果没有type=file的控件，用默认的application/x-www-form-urlencoded就可以了。 但是如果有type=file的话，就要用到multipart/form-data了。

当action为post且Content-Type类型是multipart/form-data，浏览器会把整个表单以控件为单位分割，并为每个部分加上Content-Disposition(form-data或者file),Content-Type(默认为text/plain),name(控件name)等信息，并加上分割符(boundary)。



**http响应报文：**



Response Headers里的Content-Type指服务器告诉浏览器相应的数据，类型一般有这三种：

application/x-www-form-urlencoded：数据被编码为名称/值对。这是标准的编码格式

multipart/form-data： 数据被编码为一条消息，页上的每个控件对应消息中的一个部分

text/plain： 数据以纯文本形式(text/json/xml/html)进行编码，其中不含任何控件或格式字符



Status-Code表示服务器发回的响应状态代码；Reason-Phrase表示状态代码的文本描述。状态代码由三位数字组成，第一个数字定义了响应的类别，且有五种可能取值。

- 1xx：指示信息--表示请求已接收，继续处理。
- 2xx：成功--表示请求已被成功接收、理解、接受。
- 3xx：重定向--要完成请求必须进行更进一步的操作。
- 4xx：客户端错误--请求有语法错误或请求无法实现。
- 5xx：服务器端错误--服务器未能实现合法的请求。

常见状态代码、状态描述的说明如下。

- 200 OK：客户端请求成功。
- 400 Bad Request：客户端请求有语法错误，不能被服务器所理解。
- 401 Unauthorized：请求未经授权，这个状态代码必须和WWW-Authenticate报头域一起使用。
- 403 Forbidden：服务器收到请求，但是拒绝提供服务。
- 404 Not Found：请求资源不存在，举个例子：输入了错误的URL。
- 500 Internal Server Error：服务器发生不可预期的错误。
- 503 Server Unavailable：服务器当前不能处理客户端的请求，一段时间后可能恢复正常

PHP、Java、ASP等服务器程序

PHP（HyperText Preprocessor）是一种创建动态交互性站点的强有力的服务器端脚本语言。

第一句 Hello World

echo  

<?php

​    echo 'hello word<br>'; // echo('hello word<br>');

 ?> 

输出结果为：    ![img](00-笔记_files/Image.png)





die()  >> 输出内容的同时结束程序



**1) 变量**

   

​    $num = 20;

​    echo $num;



**2)for()...**

for ($i=1; $i<=5; $i++){

​     echo "The number is " . $i . "<br>";

}

​     

​     **while**



​     $x = 1;



​     while($x < 10){

​          $x++;

​          echo $x;

​     }

​     

​     



**3) if else**



if (条件1){

​     条件1成立时执行的代码；

}elseif(条件2){

​     条件1不成立但条件2成立时执行的代码；

}else{

​    条件1条件2都不成立时执行的代码；

}





**4)变量|函数：**



其实PHP最经典，也是最核心的地方就是函数，PHP提供了超过一千种內建函数，[参考手册](http://www.w3school.com.cn/php/php_ref.asp)点击前往;



函数：function 关键字声明函数;



函数分成两个部分，一部分是函数体，另一部分是函数调用；



**函数体**：**function**(关键字) **fnName**(函数名任意值) **()**(小括号,其中可以有形参){

​          //待执行语句;



​          return //如果遇到return关键字则终止函数运行，并将return后的值作为函数的返回值;

}

例:



function fnName(){

​     

}



**函数调用**:

目的：执行函数体中待执行语句;



**fnName**(函数名) **()**(小括号,期中可以传入实参)



例:

$x = 123

fnName($x );









**超级全局变量：**



这种变量在脚本的全局都可以使用：



\- $GLOBALS



\- $_SERVER



\- $_REQUEST



\- $_POST



\- $_GET



\- $_FILES



\- $_ENV



\- $_COOKIE



\- $_SESSION



以上都是超级全局变量；







 **$_REQUEST会收集表单提交的信息；**



<html>

​    <body>

​        <form action="<?php echo $_SERVER['PHP_SELF'];?>">

​                <!-- 利用$_SERVER获取当前脚本地址  -->

​                <input type="text" name="user">

​                <input type="submit" value="处理数据">

​        </form>

​        <?php

​            if($_REQUEST){

​                $userName = $_REQUEST['user'];

​                echo $userName;

​            }

​         ?>

​    </body>

</html>



**$_POST|$_GET 用于收集表单数据，但是这里规定了发送方式，也就是表单上的method='PSOT'|method="GET"；**



<html>

​    <body>

​        <form method="POST" action="<?php echo $_SERVER['PHP_SELF'];?>">

​                <!-- 利用$_SERVER获取当前脚本地址  -->

​                <input type="text" name="user">

​                <input type="submit" value="处理数据">

​        </form>

​        <?php

​            if($_POST){

​                $userName = $_POST['user'];

​                echo $userName;

​            }

​         ?>

​    </body>

</html>











**php中的数据类型：**



共有八中数据类型：



1.boolean（布尔型）;

\2. integer（整型）; 

3.float(浮点型);

4.string(字符串)

5.array（数组）

6.object(对象)

\7. resource（资源）

8.NULL（null）













**- 数组/对象**



**1.数组是啥？**



用来储存多个数据的数据类型;



**2.创建数组：**



$arr = array(1,2,3,4,5)；



**使用数组：**



$arr[0] //1

$arr[1]//2

$arr[2]//3

$arr[3]//4

$arr[4]//5



**手动数组赋值：**



$arr[0] = 11;



数组相关方法:



获取数组长度：count()函数;



count($arr);//返回数组长度;



这样我们就可以写for循环了,数组中的内容我们就可以遍历出来了;



for($x = 0 ; $x < count($arr) ; $x++){



​     echo $arr[$x];



}



**php关联数组：（用****=>****链接起来）**



​    $testArray = array('name' => "zhangsan",'age' => 17 );



​    echo $testArray['name'].'\'s age is '.$testArray['age'];







**返回json** 



​    json_encode()方法进行json格式的转码；

​    json_decode()方法对json进行解析











数据库（database）： 按照数据结构来组织、存储和管理数据的仓库

| 商品id | 商品名称       | 销售单价 |
| ------ | -------------- | -------- |
| 1      | 老坛酸菜牛肉面 | 5        |
| 2      | 百岁山矿泉水   | 3        |
| 3      | 鼠标           | 80       |
| 4      | 水杯           | 19.9     |
| 5      | 大宝剑         | 500      |



![img](00-笔记_files/数据库.jpg)



RDBMS：关系型数据库（MongoDB  非关系型数据库）

​        DB2

​        Oracle

​        SQLServer--MSSQL

​        MySQL



SQL：结构化查询语言

​        DDL：数据定义语言

​        DCL：数据控制语言

​        DML：数据操纵语言，INSERT（添加）、UPDATE（修改）、DELETE（删除）

​        DQL ：数据查询语言，SELECT（查询）

​        **CRUD - 数据：添加（** **Create****）、查询（** **Retrieve****）、修改（** **Update****）、删除（** **Delete****）**



概念：

​        数据库：存储数据的仓库

​        表：仓库里面的房间

​        列（字段）：房间里的箱子

​        行（记录）：箱子里的数据

​        主键：唯一标识记录





使用MySQL：

​    a. 安装

​    b. 启动MySQL数据库服务

​    c. 使用mysql-front管理MySQL数据库

​      



​        \1.  建立连接

​        \2. 创建数据库

​        \3. 在数据库中创建表            数据类型：

​                字符串：char  varchar  text

​                日期时间：date、time、datetime、timestamp

​        \4. CRUD

​            插入：

​                INSERT INTO 表名(列名) VALUES (列值)

​            修改：

​                UPDATE 表名

​                SET 列名=新列值, 列名=新列值

​                WHERE 条件

​                注意，不给修改的条件（WHERE子句）则会修改整张表的数据，这种修改是不可撤销的修改

​            删除：

​                DELETE FROM 表名

​                WHERE 条件

​                注意，不给删除的条件（WHERE子句）则会删除整张表的数据，这种删除是不可撤销

​            查询：

​                SELECT 列名

​                FROM 表名

​                WHERE 条件

​                ORDER BY 排序列 ASC|DESC

​                LIMIT 起始索引, 限定行数



​                ASC-升序

​                DESC-降序



​                SELECT id, name, birthday

​                FROM students

​                ORDER BY id ASC

​                LIMIT 3, 3

​                模糊查询：

​                    LIKE

​                    SELECT id, name, birthday

​                    FROM students

​                    WHERE name LIKE '李%'

PHP连接数据库操作：

​    a. 建立连接

​        mysql_connect(servername,username,password);

​            -- servername 服务器名

​            -- username 登录数据库的用户名

​            -- password 密码

​    b. 选择数据库

​        mysql_select_db(dbname)

​    c. 设置编码

​    d. 编写SQL语句

​    e. 执行SQL语句

​        $result = mysql_query($sql);

​            -- 对 INSERT、UPDATE、DELETE 的SQL语句，返回的是布尔值：true表示SQL语句执行成功，false表示SQL语句执行失败

​            -- 对 SELECT ，返回的是查询的结果集（虚拟的表格）

​    f. 处理执行结果

​        -- 对于查询结果集，可以使用 mysql_fetch_assoc($result) 来读取查询结果集中的一行，放置到数组中保存

​    g. 关闭连接

​        mysql_close();

mysql_connect("localhost","root","");

mysql_select_db("test");

mysql_query("set charset 'utf8'");

mysql_query("set character set 'utf8'");

$sql = "SELECT * FROM user";

$result = mysql_query($sql);

while ($arr =mysql_fetch_assoc($result)) {

  echo $arr['name']." : ".$arr['age'];

}

mysql_close();

## 通信协议

通信协议

依照一种规则进行交流

浏览器  ---> 服务器之间的交流   TCP协议

TCP是面向连接的，无论哪一方向另一方发送数据之前，都必须先在双方之间建立一条连接。在TCP/IP协议中，TCP 协议提供可靠的连接服务，连接是通过三次握手进行初始化的。

三次握手

HTTP（无状态的协议）



基于TC协议的一种高级协议, 用于客户端和服务器直接的通信

这种通信最大的问题在哪？

问题就在于每次收到返回的页面后，连接都断开了。

这种通讯的问题就在于， 你挂了电话， 还怎么通讯？

比如你刚刚登陆过的账号密码， 如果你再想要登陆的话， 还要输入一遍。。。 举个简单的例子， 你逛淘宝时候每看一个商品都要重新登陆一下。。。那酸爽；

**cookie  会话跟踪技术**

一个网站从打开到浏览（包括这个网站的其他子页面）到最后关闭浏览器整个过程叫一个“会话”。

在一次会话从开始到结束的整个过程，全程跟踪记录客户端的状态（例如：是否登录、购物车信息、是否已下载、是否 已点赞、视频播放进度等等）。  

多次请求页面，数据共享

cookie的存取

document.cookie = "username=zhangsan";

console.log(document.cookie);

注意：cookie是http/https协议下的技术，大部分浏览器都不支持本地file文件对cookie操作

cookie的时效： expires

var d = new Date();

d.setxxx(); //将d设置到过期的日期

document.cookie = "username=zhangsan;expires="+d;

cookie有哪些特点？

1 只能使用文本   (如果浏览器可以随意在客户端机器上生成文件，比如身份牌是个定时炸弹，安全问题将会变得非常严重)

2 单条存储有大小限制  4KB     (文件若没有大小限制，比如身份牌的重量是140斤，挂脖子能不能累死？)

3 数量制     （一般浏览器，限制大概在50条左右，你家的门禁卡里能存的下一部蓝光高清么？

4 读取有域名限制     不可跨域读取，只能由来自 写入cookie的 同一域名 的网页可进行读取。     简单的讲就是，谁写的cookie，谁才有权利读取     （身份牌是我发你的，当然只有我能读取，你媳妇儿的手机自动连接了邻居老王家的wifi，你知道这意味着什么 吗？)

5 时效限制     每个cookie都有时效，最短的有效期是，会话级别：就是当浏览器关闭，那么cookie立即销毁     （安全学基本理论：密码锁每次打开都需要重新输入密码，输入一次密码，以后就不再验证，就没有安全可言  )        问： 信用卡为什么会有过期时间？ 

6 路径限制   存cookie的时候可以指定路径。只允许子路径读取外层cookie，外层不能读取内层

另： cookie直接存中文会造成未知错误，所以一般使用encodeURIComponent()进行编码，decodeURIComponent进行解码

**浏览器的同源策略：**



​    浏览器安全策略，保障非同源资源之间数据访问的安全性。

​    默认不允许非同源的资源直接访问。

​    URL：

​        协议://域名:端口/路径名称?查询字符串#位置标识符

​    同源：**协议、域名、端口**完全一致，只要三个中有任何一个不一致，则是非同源



​    非同源资源间需要进行访问，则需要实现跨域。



解决资源跨域访问：

​    a. CORS

​        cross-origin resource sharing

​        服务器端：

​            设置响应头信息：        Access-Control-Allow-Origin:*

​        前端：

​            ajax

​        可解决GET/POST跨域需求



​    b. jsonp

        <script src=""></script>

​        利用<script>在引入外部JS时不受同源策略限制的特性，来实现跨域。(src的开放性原则)

​        JSONP只能处理GET请求方式的跨域



​        后端：

​            由服务器端构建一个字符串：字符串中的内容是能够在 JS 中执行的函数调用的结构

​        前端：

​            \1. 创建 <script> 元素

​            \2. 设置 src 属性，传递 callback 参数指明全局回调函数的名称

​            \3. 添加到 body 中

​            \4. 创建全局函数，用于处理响应数据

​            \5. 删除 <script> 元素



​    c.   ..........



JSONP接口：

​    百度：<https://sp0.baidu.com/5a1Fazu8AA54nxGko9WTAnF6hhy/su?wd=>关键字&cb=回调函数名















## **promise（ES6）**



​    承诺：服务员承诺会把菜端上来



​    承诺：--->  兑现 （resolve）  或  失信（rejected）



​    这个对象有三种状态：Pending（进行中）、Resolved（已完成，又称 Fulfilled）和 Rejected（已失败）。只有异步操作的结果，可以决定当前是哪一种状态，任何其他操作都无法改变这个状态。这也是 Promise 这个名字的由来，它的英语意思就是「承诺」，表示其他手段无法改变。







Promise对象(ES6)：

​    用于表示一个异步操作的最终状态（完成或失败），以及其返回的值。它允许你为异步操作的成功和失败分别绑定相应的处理方法。这让异步方法可以像同步方法那样返回值，但并不是立即返回最终执行结果，而是一个能代表未来出现的结果的promise对象。

​    一个 Promise有以下几种状态:

​        pending: 初始状态，既不是成功，也不是失败状态。

​        fulfilled: 意味着操作成功完成。

​        rejected: 意味着操作失败。



​    创建Promise对象：

​        var promise = new Promise( executor );

​            executor: 是一个函数，该函数在创建Promise对象的同时被调用执行。

​            executor:

​                语法：function(resolve, reject) {...}

​                --resolve：将Promise对象状态修改为 fulfilled，可以传递参数到then方法的第一个函数中

​                --reject：将Promise对象状态修改为 rejected，可以传递参数到 then 方法的第二个函数中



​    API：

​        Promise.prototype.then(onfulfilled, onrejected) 方法：

​            -- onfulfilled 绑定的是成功时执行的函数

​            -- onrejected 绑定的是失败时执行的函数



​        Promise.all(iterable)

​            -- iterable : 可迭代对象（数组）

​            -- 返回Promise对象

​            -- 当数组中所有Promise对象都完成时，回调执行成功的函数，当只要有一个执行失败时，就回调执行失败的函数。



var promise1 = Promise.resolve(3);

var promise2 = 42;

var promise3 = new Promise(function(resolve, reject) {

  setTimeout(resolve, 100, 'foo');

});



Promise.all([promise1, promise2, promise3]).then(function(values) {

  console.log(values);

});
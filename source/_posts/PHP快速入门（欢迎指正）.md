---
title: PHP快速入门（欢迎指正）
tags: 教程
categories: PHP
keywords: PHP,编程
abbrlink: 56423
date: 2020-04-28 22:51:20
description:
cover: /img/php.jpg
---
### PHP快速入门（欢迎指正）   

#### 前言：PHP和C/JAVA什么的很像，既然大佬都会C/JAVA，那我就着重说一下区别。

#### 准备工作：安装 Wampserver，成功安装后打开的效果是绿色。 

#### PHP基本语法   

1. PHP代码可以被放在文档中的任意位置

2. PHP文件通常包含PHP和前端代码

3. PHP脚本以<?php 开始，以?&gt;结束   

   #####  实例

   ```PHP
   <?php 
   echo 'Hello World!';
   ```

   例子中我没有写?&gt;闭合标签，这是一个习惯，大多数PHP文件不用写闭合标签，IDE自动生成的代码也都没有闭合标签，只有当PHP和HTML代码交错的时候需要写?&gt;。

   ##### 实例

   ```PHP
   <div class="<?php echo 'dalao'; ?>">
   	<p><?php echo 'tql8';?></p>
   </div>
   ```
   
4. PHP使用四个空格缩进（是吗   

5. PHP语句以分号结束

6. PHP注释和C/JAVA一样  
---
#### PHP变量   

1. PHP是弱类型语言，PHP变量使用前无需声明   

2. PHP变量的格式为$变量名

   ##### 实例

   ```PHP
   <?php 
   $xclan = dalao;
   echo $xclan;
   ```

3. PHP变量使用驼峰命名法，命名规则与C/JAVA一样   

4. PHP变量有四种作用域   

   * local
   * global
   * static
   * parameter

    ##### 实例

    ```PHP
    <?php
    $a = 1;
    $b = 2;
    function dalao(){
       global $a,$b;
       $b = $a + $b;
    }
    dalao();
    echo $b;
    ```

    以上脚本的输出将是 "3"。在函数中申明了全局变量 $a 和 $b，任何变量的所有引用变量都会指向到全局变量。对于一个函数能够申明的全局变量的最大个数，PHP 没有限制。global 关键字用于函数内访问全局变量。

---
#### PHP echo/print 

1. PHP有两种输出函数，echo/print

2. 区别就是echo更快，无返回值，print恒返回1

3. echo的格式有两种，即加()或不加括号

   以下实例都是正确的   

   ##### 实例

   ```PHP
   <?php 
   echo "XCLAN";
   echo ("EndureBlaze");
   print 'Butanediol';
   ```

   可见，由于弱类型，PHP的单引号和双引号不做区分。   

---
#### PHP EOF

1. PHP EOF的作用是保持原样输出

2. 用法是 <<<EOF 原样输出的东西 EOF;

   ##### 实例

   ```PHP
   <?php 
   echo <<<EOF
   <h1>我喜欢你鸭，呐呐呐</h1>
   EOF;
   ```

   实际上EOF可以替换成任意字符   

   ```PHP
   <?php 
   $love = <<<NMSL
   <p>我爱你</p>
   NMSL;
   // 结束需要独立一行且前后不能空格
   echo $love;
   ```
   这样都行   

---
#### PHP数据类型 

1. 虽然说不用声明，但是PHP有数据类型

2. 不出你所料：String（字符串）, Integer（整型）, Float（浮点型）, Boolean（布尔型）, Array（数组）, Object（对象）, NULL（空值）

3. PHP可以使用 var_dump()函数返回变量的数据类型和值

   ##### 实例

   ```PHP
   <?php
   $a = 1;
   $dalao = '除了我';
   $flag = true;
   var_dump($dalao);
   ```
   
4. PHP数组的声明方法

   ```PHP
   <?php 
   $dalao = array("xclan","endureblaze","butanediol");
   var_dump($dalao);
   ```

---
#### PHP类型比较  

1. 松散比较：使用两个等号 == 比较，只比较值，不比较类型

2. 严格比较：用三个等号 === 比较，除了比较值，也比较类型

   ##### 实例

   ```PHP
   <?php
   if(42 == "42") {
       echo 'dalao';
   }
    
   echo PHP_EOL; // 换行符
    
   if(42 === "42") {
       echo 'tcl';
   } else {
       echo 'tql';
   }
   ?>
   ```

   输出结果是:

   dalao

   tql

---
#### PHP常量
1. 设置常量，使用 define() 函数，函数语法如下：

   ```PHP
   define ( string $name , mixed $value [, bool $case_insensitive = false ] )
   ```
   该函数有三个参数
   
   * name：必选参数，常量名称，即标志符。
   
   * value：必选参数，常量的值。
   
   * case_insensitive ：可选参数，如果设置为 TRUE，该常量则大小写不敏感。默认是大小写敏感的。    

---
#### PHP字符串变量
1. 可以使用单引号或双引号

2. strlen()函数可以返回字符串的长度

3. strpos() 函数用于在字符串内查找一个字符或一段指定的文本。如果在字符串中找到匹配，该函数会返回第一个匹配的字符位置。如果未找到匹配，则返回 FALSE。

   ##### 实例

   ```PHP
   <?php
   echo strpos("Hello world!","world");
   echo strlen("sd,tql");
   ?>
   ```

   输出结果是：66

   提示：在上面的实例中，字符串 "world" 的位置是 6。之所以是 6 而不是 7 的原因是，字符串中第一个字符的位置是 0，而不是 1。

---
#### PHP运算符

1. 算数运算符：和C一样，另有并置运算符 . 用来连接两个字符串

   ##### 实例

   ```PHP
   <?php 
   echo "XCLAN" . "是" . "dalao";
   ```

2. 赋值运算符：和C一样

3. 自增自减运算符：和C一样

4. 比较运算符：多了 === , != 和 !== （大佬能理解

5. 逻辑运算符：and（与），or（或），xor（异或），&&（与），||（或），!（非）

6. 数组运算符：

   * x + y 集合，x 和 y 的集合

   * x == y 相等， 如果 x 和 y 具有相同的键/值对，则返回 true

   * x === y 恒等， 如果 x 和 y 具有相同的键/值对，且顺序相同类型相同，则返回 true

   * x != y x<>y 不相等， 如果 x 不等于 y，则返回 true

   * x !== y 不恒等， 如果 x 不等于 y，则返回 true

7. 三元运算符：和C一样

8. 组合比较符（PHP7+）：语法格式如下

   ```PHP
   $c = $a <=$b;
   ```

   * 如果 $a $b,则$c的值为1。

   * 如果 $a == $b,则$c的值为0。

   * 如果 $a < $b,则$c的值为-1。

---
#### PHP条件分支语句

1. if else语句：和C一样，区别是elseif中间没有空格

2. switch语句：和C一样

---
#### PHP数组

1. 创建数组使用array()函数

2. count()函数可用于获取数组长度

3. 使用变量名[下标]访问数组

4. 关联数组：关联数组是使用您分配给数组的指定的键的数组，这里有两种创建关联数组的方法：

   ##### 实例

   ```PHP
   <?php 
   //第一种
   $age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
   //第二种
   $age['Peter']="35";
   $age['Ben']="37";
   $age['Joe']="43";
   ```
   遍历并打印关联数组中的所有值，您可以使用foreach循环，如下所示：
   ```PHP
   <?php
   $age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
    
   foreach($age as $x=>$x_value)
   {
       echo "Key=" . $x . ", Value=" . $x_value;
       echo "<br>";
   }
   ?>
   ```
   
5. 多维数组：包含一个或多个数组的数组，如下所示：

   ##### 实例

   ```PHP
   <?php
   $sites = array
   (
       "Butanediol"=>array
       (
           "丁二大佬",
           "http://blog.丁二购买了一个.网址"
       ),
       "Endureblaze"=>array
       (
           "炎忍大佬",
           "http://blog.endureblaze.cn"
       ),
       "xclan"=>array
       (
           "小苍兰大佬",
           "http://www.watashimo.xyz"
       )
   );
   print("<pre>"); // 格式化输出数组
   print_r($sites);
   print("</pre>");
   ?>
   ```
   
6. 数组排序：PHP提供了几种数组排序函数：

   * sort() - 对数组进行升序排列

   * rsort() - 对数组进行降序排列

   * asort() - 根据关联数组的值，对数组进行升序排列

   * ksort() - 根据关联数组的键，对数组进行升序排列

   * arsort() - 根据关联数组的值，对数组进行降序排列

   * krsort() - 根据关联数组的键，对数组进行降序排列

---
#### PHP超级全局变量

1. PHP中预定义了几个超级全局变量（superglobals） ，这意味着它们在一个脚本的全部作用域中都可用。 你不需要特别说明，就可以在函数及类中使用。

   * $GLOBALS

   * $\_SERVER

   * $\_REQUEST

   * $\_POST

   * $\_GET

   * $\_FILES

   * $\_ENV

   * $\_COOKIE

   * $\_SESSION

   太多了⑧，我就说几个常用的吧

2. $\_POST（$\_REQUEST和$\_GET差不多，可以去找找资料）被广泛应用于收集表单数据，在HTML form标签的指定该属性："method="post"。当用户点击submit时，会将form表单的数据提交给PHP，我们可以使用$\_POST来收集表单中input字段的数据

   ##### 实例

   ```PHP
   <html>
   <body>
    
   <form method="post" action="<?php echo $_SERVER['PHP_SELF'];?>">
   Name: <input type="text" name="fname">
   <input type="submit">
   </form>
    
   <?php 
   $name = $_POST['fname']; 
   echo $name; 
   ?>
    
   </body>
   </html>
   ```
   当用户点击submit按钮时，会显示用户在输入框中输入的内容

---
#### PHP循环
1. for while do-while循环：和C一样

2. foreach 循环用于遍历数组：

   ```PHP
   <?php
   foreach ($array as $value)
   {
       要执行代码;
   }
   ```
   
   每进行一次循环，当前数组元素的值就会被赋值给 $value 变量（数组指针会逐一地移动），在进行下一次循环时，您将看到数组中的下一个值。
   
   ##### 实例
   
   ```PHP
   <?php
   $x=array("one","two","three");
   foreach ($x as $value)
   {
       echo $value . "<br>";
   }
   ?>
   ```

---
#### PHP函数

1. PHP使用function关键字来创建函数，无需声明其数据类型（

2. 使用驼峰命名法

   ##### 实例

   ```PHP
   <?php
   function writeName()
   {
       echo "dalao";
   }
    
   echo "My name is ";
   writeName();
   ?>
   ```

   3. 参数、返回值：和C一样

---
#### PHP魔术常量
1. \_\_LINE__：文件中的当前行号

2. \_\_FILE__：文件的完整路径和文件名。如果用在被包含文件中，则返回被包含的文件名。（绝对路径，怕了）

3. \_\_DIR__：文件所在的目录。如果用在被包括文件中，则返回被包括的文件所在的目录。除非是根目录，否则目录中名不包括末尾的斜杠

4. \_\_FUNCTION__：函数名称（PHP 4.3.0 新加）。自 PHP 5 起本常量返回该函数被定义时的名字（区分大小写）。在 PHP 4 中该值总是小写字母的。

5. \_\_CLASS__：类的名称（PHP 4.3.0 新加）。自 PHP 5 起本常量返回该类被定义时的名字（区分大小写）。

6. ……有点多，还是查资料吧

#### ……先写这么多吧

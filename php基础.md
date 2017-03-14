#PHP

##资源
>我们开发都是在开发资源，开发好资源然后吧资源部署到服务器，然后客户端就可以访问我的资源

资源分为两种：
 1.静态资源：可以直接通过浏览器打开 **html css js image**
 2.动态资源：需要被服务器转换成静态资源 **php jsp asp**

开发动态资源：开发好之后吧动态资源部署到服务器
动态资源跟静态资源，静态资源是由浏览器解析的，动态资源是在服务器运作的

##动态资源php

###php代码必须写在<?php ?>中

###定义变量
$username="";
输出
echo "";

###php中变量的类型

###1. 字符串
>    $username="王五";
>
>    echo "username";

###2. 整型
>    $age=11;

###3. 浮点型
>    $price=11.11;

###4. 布尔类型
>    $flag=true;
>    echo $flag;
>    如果是true  输出1
>    如果是false  什么都不输出

###5. 数组
>    php里面有两种类型的数组
>    普通数组和关联数组
>

####普通数组

怎么定义一个普通数组
通过array函数定义
```
$array1=array("zhangsan","lisi");
```
遍历数组 使用for循环
目的是想获取数组的长度
php有一个函数是用来获取数组长度的
```
$length = count($array1);
for($i=0;$i<count($array1);$i++){
  echo $array1[$i];
  echo "<br>";
}
```

####关联数组
数组是用来存放数据的  关联数组里面的数据有关联关系
之前学习的数组的关联关系，键值对，通过key 可以找到值
```
$array2 = array("username"=>"zhangsan","age"=>11);
```

根据key去获取值
```
echo $array2["username"];
echo $array2["age"];
```


####二维数组
```
$array3=array(
	array("username"=>"zhangsan","age"=>13),
	array("username"=>"lisi","age"=>"14")
)
```
###6.php的字符串链接使用 . 链接相当于javascript中的+

###7.php中的函数 function doubleKill(){}     doubleKill();
>php函数的参数可以设置一个默认值 不设置默认值不传值发生错误 设置默认值 不传值就使用默认值

###8.php当中的输出
```
echo "";
print_r() 输出一个数组或对象的
var_dump()  输出一个数组中的相信信息
```
###9.php 当中常见的函数
count()  in_array()  array_key_exists()  file_get_contents()  
move_upload_file(); 移动上传的文件

##客户端与服务器进行交互的时候怎么进行数据传递

###1.客户端怎么提交
	三种方式，地址栏输出，超链接(href，src) 表单提交
	提交是给服务器发送数据
	提交有两种方式
		get，地址栏输出超链接(href，src) 表单提交默认是get
		post，表单提交我可以设置成post
	发送参数
		get 提交 地址?paraName=value&paraName=value
		post 提交 表单提交会自动帮我把数据发送到服务器
###2.服务端
	做哪些事情
	1：接受请求
		$_GET $_POST 这两个变量得到的值都是一个关联数组
		客户端的数据放在关联数组里面，我要取数据，根据key去获取
	2：处理请求
		链接数据库，增删改查
	3：响应数据
		echo 根据处理请求的逻辑，给客户端不同的响应结果
	案例 用户登录
###3.文件上传
	客户端
		1：表单提交
		2：post方式提交
		3：必须有一个input type=file
		4：必须给form 设置一个属性enctype="multipart/form-data";
	服务端：
		接收数据
		$_FILES 接受到的数据也是一个关联数组
		
		一般情况下，把这个里面的数据$_FILES取出来
		里面客户端上传过来的数据，我一般再次进行一个处理，保存
###4.动态输出
	<?php if(true){?>
	<?php }?>
	<?php for($i=0;$i<=1000;$i++){?>
	<?php }?>
动态输出小案例 查询用户


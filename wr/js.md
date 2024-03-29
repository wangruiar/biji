# 笔记

## JavaScript 

```
JS 是一种网页编程技术 , 用于向网页添加交互行为的编程技术 . 
JS 是一种基于对象 和 事件驱动的 解释性脚本语言 ,由浏览器直接解析执行代码 , 不进行预编译.

特点:
	1.	JS代码可以直接嵌入到HTML文件中
	2.	可以使用任何的文本编辑器编写代码 
	3.	基于对象 内置了大量的可用对象.
	4.	与Java不同, 代码不进行预编译, 直接解析执行.

缺点:
	不具备计算机本地资源的操作能力. 

作用:

 	1.	客户端的逻辑运算
 	2.	网页事件处理
 	3.	表单的合法性验证
 	4.	动画效果制作
 	
     可以减轻服务器的压力.
```

#### 定义js代码方式

```
1.	定义在元素的事件属性中
		<button onclick="alert('文字内容')">按钮</button>

2.	定义在网页的script标签中
		<script type="text/javascript">
			for(i=0;i<100;i++){
				alert("恩恩呢"+i);
			}
		</script>
3.	定义在外部的.js文件中.
		<script type="text/javascript" src="js/demo1.js"></script>
		                           |上面的是自动生成        |地址自动生成
```

#### js弹出窗

```
任何的JS弹出窗 , 都会导致浏览器的线程阻塞! 程序等待用户点击关闭 再向下执行.

1.	提示窗口
		alert("弹出的内容");

2.	弹出信息问询框 , 具备确定和取消按钮, 点击确定时 返回true ,点击取消或关闭时返回false
		confirm("弹出的内容");

3.	弹出输入框 , 具备确定和取消按钮 ,点击确定返回输入内容, 点击取消或关闭 返回null
		prompt("提示输入的内容");
```

#### 定义变量

```
语法格式:	var 变量名 = 初始化值;
```

#### 数据类型

```
-	基本数据类型
		-	number	:	数值型.
		-	boolean	:	布尔类型
		-	string	:	字符串类型

-	复杂数据类型
		-	Array	:	数组
		-	Object	:	对象

-	特殊数据类型
		-	null	:	空
		-	undefined:	未定义  , 未定义的数据 判断是否等于null时, 结果为true
```

#### 正则表达式

```
正则表达式：是对字符串操作的一种逻辑公式，就是用事先定义好的一些特定字符、及这些特定字符的组合，组成一个“规则字符串”，这个“规则字符串”用来表达对字符串的一种过滤逻辑。

给定一个正则表达式和另一个字符串，我们可以达到如下的目的：
1. 给定的字符串是否符合正则表达式的过滤逻辑（称作“匹配”）：
2. 可以通过正则表达式，从字符串中获取我们想要的特定部分。

正则表达式的特点是：
1. 灵活性、逻辑性和功能性非常强；
2. 可以迅速地用极简单的方式达到字符串的复杂控制。
3. 对于刚接触的人来说，比较晦涩难懂。

使用步骤
	1.	创建正则对象
			var 对象名 = /正则表达式/g;
	2.	使用
			正则对象.test(要验证的数据)	:	返回boolean类型的值, 符合true , 不符合false
```

#### 函数

```
定义函数的格式:

	function 函数名(形式参数列表){
		//函数体
	}

案例:
	定义一个函数, 拥有两个参数, 用于计算两个参数的和 , 并将计算结果返回

	function sum(x,y){
		return x+y;
	}
```


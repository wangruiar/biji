# JavaScript笔记

### 简介

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
		
	可以减轻服务器的压力

### 定义JS代码的三种方式 

	1.	定义在元素的事件属性中
			<button onclick="alert('从前有座山')">按钮</button>
	
	2.	定义在网页的script标签中
			<script type="text/javascript">
				for(i=0;i<100;i++){
					alert("嘿嘿嘿"+i);
				}
			</script>
	3.	定义在外部的.js文件中.
			<script type="text/javascript" src="js/demo1.js"></script>

### JS的三种弹出窗


	任何的JS弹出窗 , 都会导致浏览器的线程阻塞! 程序等待用户点击关闭 再向下执行.
	
	1.	提示窗口
			alert("弹出的内容");
	
	2.	弹出信息问询框 , 具备确定和取消按钮, 点击确定时 返回true ,点击取消或关闭时返回false
			confirm("弹出的内容");
	
	3.	弹出输入框 , 具备确定和取消按钮 ,点击确定返回输入内容, 点击取消或关闭 返回null
			prompt("提示输入的内容");

### 定义变量 

	语法格式:	var 变量名 = 初始化值;

### 如何获取变量值类型 

	JS提供了一个函数, 可以用于获取变量值的类型
		typeof(变量)	:	返回字符串, 是类型的名称


	案例:
		<script type="text/javascript">
			var a = 10;
			alert(typeof(a)+":"+a);
			a = false;
			alert(typeof(a)+":"+a);
			a = "锄禾日当午";
			alert(typeof(a)+":"+a);
		</script>


### 正则表达式对象

	使用步骤
		1.	创建正则对象
				var 对象名 = /正则表达式/g;
		2.	使用
				正则对象.test(要验证的数据)	:	返回boolean类型的值, 符合true , 不符合false


### 函数 *****

	定义函数的格式:
	
		function 函数名(形式参数列表){
			//函数体
		}
	
	案例:
		定义一个函数, 拥有两个参数, 用于计算两个参数的和 , 并将计算结果返回
	
		function sum(x,y){
			return x+y;
		}
	
	练习:
		定义一个函数, 函数中拥有四个参数 , 比较四个参数的大小, 将最大的参数值 返回.
		function max(q,w,e,r){
			return ((q>w?q:w)>e?(q>w?q:w):e)>r?((q>w?q:w)>e?(q>w?q:w):e):r;
		}

### Date函数

	new Date();        		 					   时间对象
	date.getTime();   						   转换成时间戳
	date.getFullYear() + '年';     		获取完整的年份
	date.getMonth()+ 1 + '月';  		 获取月份
	date.getDate() + '日  '; 			   获取日
	date.getHours() + '时';  			 获取小时数
	date.getMinutes() + '分';  		   获取分钟数
	date.getSeconds() + '秒';  		  获取秒数

### 选择语句

```
switch(a){		
				case "yyyy":    //如果
				alert(Y);       //就
				break;       //返回
```

### 截取

```
alert(phone.slice(0,phone.indexOf("@")));
//从开始到@符号之间的所有内容
```


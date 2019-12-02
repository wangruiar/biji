# Jquery 01

2019/10/28 8:57:21 

----

###介绍

	Jquery是一个快速的简单的JavaScript代码库 , 也可以看做一个 JavaScript 框架.


​	
###使用步骤:

	其实Jquery就是一个别人写好的js文件 , 将其引入到html中, 就可以了.


	下载Jquery.js文件 , 引入到HTML中. 
		步骤1.	下载:https://cdn.bootcss.com/jquery/3.4.1/jquery.js
		步骤2.	通过script标签引入.
	
	或 直接引入知名CDN的框架文件 , 开发时更建议.
		<script src="https://cdn.bootcss.com/jquery/3.4.1/jquery.js"></script>


​		
### onload 使用

	格式:
		$(function(){
			//	当网页加载完毕时, 执行
		});


### Jquery对象

	我们在JS中, 通过文档对象 , 查找的是元素对象.   网页中DOM.
	Jquery将网页中的元素, 封装为了Jquery对象 , 可将将Jquery对象 看作 dom对象的集合.

#### DOM对象 与 Jquery对象 互相转换

	DOM对象无法操作 Jquery对象的API    
	Jquery对象 也 无法操作 DOM对象的api  
	
	DOM对象 转换为 Jquery对象:
		格式: var $obj = $(dom对象);


	从Jquery对象中 取出其中的DOM对象 : 
		格式:	var dom = $obj.get(下标);



### Jquery 选择器 *

	我们学习的CSS的选择器, 都可以应用到Jquery中.
	
	格式:
		var $obj =  $("选择器");

#### 基本选择器 *****

	-	id选择器
			var $obj = $("#id值");
	-	类选择器
			var $obj = $(".class值");
	-	元素名称选择器
			var $obj = $("元素名称");

#### 筛选选择器

	从选择器选择的结果中, 再筛选出需要的部分.

##### 基本筛选选择器 熟悉

	格式:
		选择器:first	:	选择 匹配选择器的 第一个元素.
		选择器:last	:	选择 匹配选择器的 最后一个元素.
		选择器:eq(下标) : 选择 匹配选择器的 指定下标的元素.		*
		选择器:gt(下标) : 选择 匹配选择器的 大于指定下标的元素.
		选择器:lt(下标) : 选择 匹配选择器的 小于指定下标的元素.
		选择器:even	:	选择 匹配选择器的 偶数下标的元素
		选择器:odd	:	选择 匹配选择器的 奇数下标的元素

##### 排除筛选选择器 熟悉

	格式:
		选择器1:not(选择器2)
	
	从选择器1的结果中, 排除选择器2的部分.

##### 内容筛选选择器 了解
	用于筛选内容是否包含:
		选择器:contains('包含的文本')


##### 可见性筛选选择器 了解

	可见筛选:
		选择器:visible
	不可见筛选:
		选择器:hidden
	
	什么元素是不可见:
		1.	display:none
		2.	宽度或高度或透明度 0
		3.	input标签 type=hidden

##### 表单筛选选择器 了解

	筛选input标签的type属性值
	
	格式1:	筛选网页中所有的input标签
			:type属性值
	
	格式2:	筛选匹配选择器的 input 标签
			选择器:type属性值

##### 属性筛选选择器 了解

	-	筛选属性是否存在
			选择器[属性名]
	
	-	筛选属性值 是否 等于某值
			选择器[属性名='值']
	
	-	筛选属性值 是否不等于 某值
			选择器[属性名!='值']

#### Jquery对象常用函数:

	1.	淡入淡出 函数:
			淡入:	jquery对象.fadeIn(数值毫秒);
			淡出:	jquery对象.fadeOut(数值毫秒);
	
	2.	CSS函数, 用于修改元素的样式.
	
			$obj.css("样式名称","样式的值");


### 通过Jquery对象 修改元素的属性 *

	JS:
		取出属性:	dom对象.属性名;
		设置属性:	dom对象.属性名 = 值;
	
	Jquery 中 将属性的获取与设置子, 封装为了一个函数, attr
	
		格式1. 用于一次操作单个属性.
			设置属性:	$obj.attr("属性名","属性值");
			取出属性:	var 属性值 = $obj.attr("属性名");
	
		格式2.	用于一次设置多个属性值
			$obj.attr(对象);
			//	对象中包含的属性名 和 属性值, 都会设置到元素上.
			//例如:
				var x1 = new Object();
				x1.src = "images/1.jpg";
				x1.style = "width:200px";
	
				$img.attr(x1);
			
			也可以编写为:
				$img.attr({"src":"images/1.jpg","style":"width:200px"});


####  特殊属性修改

##### class属性
	格式:
		-	添加class值
				$obj.addClass("值");
		-	删除class值
				$obj.removeClass("值");
		-	替换class值 (值存在则删除, 不存在则添加)
				$obj.toggleClass("值");

##### value属性

	通过jquery  获取输入框的内容, 使用attr函数 获取value 会出错: 得不到最新的值;
	
	Jquery 提供了一个函数, 用于获取value属性值
	
	设置值:
		$obj.val(值);
	获取值:
		var val = $obj.val();

##### 标签内容 innerHTML属性.


	格式1.
		使用html函数 
	
		设置内容:
			$obj.html(内容);
		获取内容:
			var 内容 = $obj.html();
	
	格式2.
		使用text函数
	
		设置内容:
			$obj.text(内容);
		获取内容:
			var 内容 = $obj.text();

##### JS常见面试题: ***

	Jquery中 , html函数 以 text函数, 在获取元素内容上, 有什么区别?
	
	答:
		html函数与text函数, 都用于获取元素的内容.
		区别是:
			html函数 在获取内容时,  会得到html标签部分
			text函数 在获取内容时, 会忽略html标签部分
	
		例如: 获取如下div
			<div>从前有<span>座</span>山</div>
			html函数:	从前有<span>座</span>山
			text函数:	从前有座山 















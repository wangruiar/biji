# Jquery 02

2019/10/29 11:52:05 

-----

### 样式函数 css

	用于修改样式:
	
	格式1: 一次修改单个样式
			$obj.css("样式名称","样式值");
		
	格式2: 一次修改一组样式
			$obj.css(对象);
			对象中包含的属性 , 都会设置到样式上.
	
			例如: 给所有的div 添加宽度和高度
			$("div").css({
				"width":"200px",
				"height":"200px"
			});

### 显示隐藏函数 

	-	基本显示隐藏
			-	显示:	$obj.show();
			-	隐藏:	$obj.hide();
			-	切换:	$obj.toggle();
		
	-	左上角折叠淡入淡出
			-	显示:	$obj.show(毫秒数值);
			-	隐藏:	$obj.hide(毫秒数值);
			-	切换:	$obj.toggle(毫秒数值);


	-	上下折叠
			-	显示:$obj.slideDown(毫秒数值);
			-	隐藏:$obj.slideUp(毫秒数值);
			-	切换:$obj.slideToggle(毫秒数值);
			
	-	淡入淡出
			-	淡入:	$obj.fadeIn(毫秒数值);
			-	淡出:	$obj.fadeOut(毫秒数值);


### 动画函数 

	格式:
		$obj.animate(style,time,[function]);
		参数1.	stlye:	是一个对象参数 , 描述的是动画执行完毕时的 元素样式.
		参数2.	time :	从当前样式 过渡到 目标样式 , 过渡的毫秒时长
		参数3.	function : 函数, 可选参数. 是动画执行完毕的 事件监听函数


### Jquery 事件 * 

	JS事件使我们的视图代码 html  与 逻辑代码 js混合. 不利于后期的扩展和维护.
	Jquery事件 可以很好的 使HTML代码 与 JS代码分离. 更利于扩展和维护.

#### 事件的绑定与解绑

	格式:
		-	绑定事件 (一个元素可以绑定多个同类事件.)
				$obj.bind("事件类型",function);
		-	解绑事件 (一次同种类的所有事件)
				$obj.unbind("事件类型");
		-	模拟触发事件
				$obj.trigger("事件类型");


	上述描述的事件类型, 指的是绑定的事件种类.
		比如: 点击事件的类型是: click .
		比如: 失去焦点事件的类型是: blur
	
	案例:
		<script type="text/javascript">
			//用于标记, 减号是否存在事件
			var flag = false;
			function x1(){
				var val = $("input").val();
				var num = parseInt(val);
				num++;
				$("input").val(num);
				if(num > 1 && flag == false){
					//当数字被加到2以后, 我们给减号添加点击事件
					$("button:eq(1)").bind("click",x2);
					flag = true;
				}
			}
			function x2(){
				var val = $("input").val();
				var num = parseInt(val);
				num--;
				$("input").val(num);
				if(num == 1){
					//解除减号的事件 , 并设置flag 为false
					$("button:eq(1)").unbind("click");
					flag = false;
				}
			}
			$(function(){
				//网页加载完毕时, 给+号绑定事件
				$("button:eq(0)").bind("click",x1);
			});
		</script>
		</head>
		<body>
			<button>+</button>
			<input value="1">
			<button>-</button>

#### 事件函数

	格式:	
		$obj.事件类型(function(){
			//当此类型事件发生时, 执行函数
		});


### 文档函数

#### 文档查找函数 

	根据一个已经存在的Jquery对象 , 查找与其相关的其他Jquery对象.
	
	格式:
		-	查找子元素
				$obj.children("选择器");
		-	查找后代元素  * 
				$obj.find("选择器");
		-	查找下一个兄弟元素
				$obj.next();
		-	查找上一个兄弟元素
				$obj.prev();
		-	查找父元素 *
				$obj.parent();
		-	查找祖先元素
				$obj.parents("选择器");
	
	案例:


#### 文档处理函数

	-	创建元素
			var $obj = $("html字符串");
			例如, 创建一个div,
			var $div = $("<div></div>");
	-	添加元素
			-	向父元素内部 追加子元素
					$父元素.append($新元素);
			-	向父元素内部 前置子元素
					$父元素.prepend($新元素);
	
			-	向某个元素的后面, 加入 兄弟元素
					$obj.after($新元素);
			-	向某个元素的前面, 加入 兄弟元素
					$obj.before($新元素);
	-	删除元素
			格式:	$obj.remove();
	
	-	清空元素
			$obj.html("");
			或
			$obj.empty();
	-	克隆元素
			忽略事件 克隆元素
				格式:	var $新对象 = $obj.clone();
			携带事件 克隆元素
				格式:	var $新对象 = $obj.clone(true);

### Jquery 插件

#### 二维码生成 

	步骤:
		1.	引入jquery.js
		2.	引入插件的js文件 (jquery.qrcode.js , utf.js)
		3.	在需要展示二维码的位置, 定义一个div , 并给div指定id
		4.	创建一个JS中的对象 , 描述二维码的规格 和 内容.
				var obj = {
					width:数字,//表示px
					height:数字,//表示px
					text:"二维码的内容"
				};
	
		5.	通过选择器, 选择div , 并将二维码生成到div中
				$("#div的id").qrcode(obj);

#### layer(弹出层插件) 插件 

	步骤:
		1.	引入Jquery.js
		2.	引入插件的layer.js
			需注意: layer的js文件 ,有很多的依赖 . 需要将插件的整个文件夹一起导入.


##### layer - msg 函数

	用于弹出信息提示窗, 提示窗会自动消失.
	
	格式1
		layer.msg("文字");
	
	格式2.
		弹出抖动的提示窗
		layer.msg("文字",function(){});
	
	格式3.
		带有图片的提示窗
		layer.msg("文本",{"icon":图片编号});
	
		图片编号: 0-16  (很多图片编号已经废弃了.)


##### layer - load 函数

	格式1.	弹出窗口, 使用代码关闭
	
			-	弹出load窗口,  并得到窗口的索引值
					var index = layer.load(0-2);
	
			-	关闭load窗口
					layer.close(index);
	
	格式2.	弹出窗口, 设置定时关闭 , (也可以使用代码 主动关闭)


​			
			-	弹出load窗口,  并得到窗口的索引值
					var index = layer.load(0-2,{"time":毫秒});
	
			-	关闭load窗口
					layer.close(index);

##### layer - 关闭弹出窗

	layer.closeAll();  
	可以关闭 layer弹出的所有内容.




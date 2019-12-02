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

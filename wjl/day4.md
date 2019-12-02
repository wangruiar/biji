事件函数

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




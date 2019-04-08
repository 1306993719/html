## 多列布局(分栏布局)
	1.设置栏数(最大栏数)
	语法：
		column-count:数值;
	
	2.设置每栏的宽度(最小宽度)
	语法：
		column-width:数值+单位;
	
	3.设置栏间距
	语法：
		column-gap:数值+单位;
	
	4.设置栏分隔线
	语法：
		column-rule:5px solid|dashed|dotted 颜色;
	
	5.设置是否跨栏显示
	语法：
		column-span:all(是)|none(否);
	
	注：
		给需要跨栏显示的元素添加该属性

## 弹性布局
	语法：
		display:flex;
	
	♥ 说明：
		a) 给元素设置 display:flex; 后就成为了弹性盒
		b) 当父元素设置了弹性盒后，子元素的float,clear,vertical-align将会失效
		c) 我们把设置了display:flex;的父元素称之为Flex容器，把里面的子元素称之为Flex项目
		d) 当元素设置了display:flex;后会产生两根轴线：主轴和交叉轴(侧轴)
	
	◆ Flex容器属性

### 设置主轴的方向(flex项目排列的方向)
	语法：
		flex-direction:row|row-reverse|column|column-reverse;
		row                 默认值，主轴在水平方向，起点在左端
		row-reverse         主轴在水平方向，起点在右端
		column              主轴在垂直方向，起点在上沿
		column-reverse      主轴在垂直方向，起点在下沿

### 设置flex项目一行还是多行显示
	语法: 
		flex-wrap:nowrap|wrap|wrap-reverse;
		nowrap   默认值，flex项目在一行显示
		wrap     flex项目多行显示
		wrap-reverse    flex项目多行显示，行的顺序是倒过来的	

### flex-direction和flex-wrap的简写方式
	语法：
		flex-flow:row nowrap;  (默认值)	

### 设置主轴对齐方式
	语法：
		justify-content:flex-start|flex-end|center|space-between|space-around;
		flex-start   对齐主轴的起点，当主轴在水平方向时，类似于左浮动
		flex-end     对齐主轴的终点，当主轴在水平方向时，类似于右浮动
		center       居中对齐
		space-between   flex项目两端对齐，中间间隔相等
		space-around    flex项目两侧间隔相等	

### 设置交叉轴对齐方式(侧轴）
	语法：
		align-items:flex-start|flex-end|center|baseline|stretch;
		flex-start   对齐交叉轴的起点
		flex-end     对齐交叉轴的终点
		center       以交叉轴为参考，居中对齐
		baseline     flex项目第一行文字基线对齐
		stretch      flex项目高度为auto或不设置高度，将占满整个父元素的高度		
	
	★ 使用弹性布局(flexbox)的方式来实现未知大小的元素在屏幕窗口水平垂直都居中
	语法：
		html,body{height:100%}
		body{display:flex;justify-content:center;align-items:center;}
	
	★ 使用弹性布局(flexbox)的方式来实现未知大小的子元素在父元素中水平垂直都居中
	语法：
		父元素{display:flex;justify-content:center;align-items:center;}		

### 设置多根轴线对齐方式(如果只有一根轴线，该属性不起作用)
	语法：
		align-content:flex-start|flex-end|center|space-between|space-around|stretch;
		flex-start       对齐交叉轴的起点
		flex-end         对齐交叉轴的终点
		center           以交叉轴为参考，居中对齐
		space-between    交叉轴两端对齐，轴线之间的间隔平均分布
		space-around     flex项目（沿交叉轴方向）之间的间隔相等
		stretch          flex项目默认没有设置高度或者为auto,将占满整个父元素的高度

## Flex项目属性
	1.设置flex项目排列顺序
		语法：
			order:数值;
		注：
			值越小越靠前
	
	2.设置某个flex项目不同于其他flex项目的交叉轴对齐方式
		语法：
			align-self:flex-start|flex-end|center|baseline|stretch;
	
	3.设置flex项目放大比例
		语法：
			flex-grow:0|1|数值;
		注：
			flex-grow默认值为0，即使父元素存在剩余空间，flex项目也不放大
			设置flex-grow为1时flex项目等比例放大
	
	4.设置flex项目缩小比例
		语法：
			flex-shrink:1|0|数值;
		注：
			flex-shrink默认值为1，当父元素空间不足时，flex项目等比例缩小
			flex-shrink为0时，即使父元素空间不足，flex项目也不缩小
	
	5.在分配剩余空间之前，设置flex项目占据主轴的空间
		语法：
			flex-basis:auto|数值|百分比;
		注：
			flex-basis的默认值为auto
	
	6.flex-grow,flex-shrink,flex-basis的简写方式
		语法：
			flex:0 1 auto; (默认值)
		注：
			flex:1; 等价于  flex:1 1 0%;
	
	应用1: flex项目等比例分配空间
	应用2: 分配剩余空间给某个flex项目

## 响应式布局(responsive)
	1.概念
		2015年5月份提出的一个概念，简而言之，就是一个网站可以兼容多个终端—而不是为每一个终端做一个特定的版本。
	
	优点：
		灵活性更强，解决了多设备适应问题
	
	缺点：
		工作量变大，加载时间变长
	
	核心原理：
		媒体查询
	
	2.外联式媒体查询
	语法：
		<link rel="stylesheet" type="text/css" media="screen and (min-width:960px)"  href="red.css"/>
		<link rel="stylesheet" type="text/css" media="screen and (max-width:960px)" href="blue.css"/>
	
	注：
		当屏幕窗口宽度大于等于960px时，引入red.css文件
		当屏幕窗口宽度小于等于960px时，引入blue.css文件
	
	3.内嵌式媒体查询
	语法：
		@media screen and (min-width:640px) and (max-width:960px){
	  		body{
	  			background:blue;
	  		}
	  }
	当屏幕窗口宽度大于等于640px并且小于等于960px时，body背景色为蓝色

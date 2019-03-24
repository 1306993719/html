# 常见的三种布局模型

## 流动模型（Flow）

	元素会按照本身的特征显示在网页中，块元素自上而下排列，内联元素在一行逐个进行显示
	
## 浮动模型（Float）

	运用float进行页面布局

	注：
		float对块元素和内联元素的影响
		a) 给块元素设置float后，会脱离默认文档流，在一行显示，如果没有设置宽度的情况下，宽度由内容撑开
		b) 给内联元素设置float后，就相当于转换为了块元素，可以设置宽高及任意margin,padding和border
		
## 层模型（Layer）

	语法： 
		position:static(默认值)|absolute(绝对定位)|relative(相对定位)|fixed(固定定位)；
		
# 定位

## 绝对定位

	语法：
		position:absolute;

	参照物：
		离绝对定位元素最近的具有定位属性的父包含块
		如果找不到满足条件的父包含块，那么相对于浏览器窗口进行绝对定位

	注：
		通过left,right,top,bottom中的任意两个属性来确定元素绝对定位的位置
		
## 相对定位

	语法：
		position:relative;

	参照物：
		元素偏移前的位置

	Tip： 相对定位和绝对定位的区别
	a) 参照物不同
		绝对定位的参照物是离它最近的具有定位属性的父包含块，相对定位的参照物是元素偏移前本身的位置
	b)是否会脱离文档流
		相对定位不会脱离文档流，原来的位置保留，不会被其他元素占据，绝对定位会脱离文档流，位置不保留，原位置会被其他元素占据	
		
## 固定定位

	语法：
		position:fixed;

	参照物：
		浏览器窗口(屏幕窗口)

	注：
		a) 固定定位会脱离文档流，原来的位置会被其他元素占据
		b) 当固定定位和绝对定位的参照物都是屏幕窗口时，固定定位不会跟随滚动条滚动，固定在某个位置上
		
# 透明度的设置

	语法：
		opacity:数值;   （取值范围0-1,0为完全透明，1为完全不透明）

	eg: 
		opacity:0.6;   等价于  opacity:.6;

	注：
		低版本的IE浏览器（IE8及以下浏览器）不识别opacity属性，兼容写法如下：
		filter:alpha(opacity=数值);   取值范围(0-100)
		
# 定位元素层叠属性

	语法：
		z-index：auto(默认值)| 整数值；

	注：
		a） z-index可以设置负值
		b）没有设置z-index时，最后写的对象优先显示在上层，设置后，数值越大，层越靠上；
		c） 具有定位属性的元素设置z-index有效
		
# 锚点链接

	作用：
		实现在本页面内不同位置的跳转

	语法：
		命名锚记名   <标记  id="锚记名"></标记>
        连接锚记名   <a href="#锚记名"></a>

	eg: 
		<a href="#boy">第一章 html基础</a>
		<div id="boy">html常用标记</div>
		
# 扩展

## 如何在网页中插入flash

	语法：
		<object width="1000"  height="500">
            <param name="movie" src="1.swf"/>
            <embed width="1000" height="500" src="1.swf"></embed>
        </object>

	注：
		embed标记主要用来兼容IE浏览器

## 滚动字幕

	语法：
		<marquee behavior="scroll|alternate" width="数值" height="数值" direction="left|right|up|down" scrollamount="数值">滚动内容...</marquee>

	注： 
		a) behavior="alternate"   正反方向交替运动
        b) direction    设置滚动的方向
        c) scrollamout   设置滚动的速度，值越大，速度越快
		
		
		
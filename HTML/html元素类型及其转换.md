# html元素分类

	html元素分为三类：块元素，内联元素，可变元素
	注：
		可以将html元素分为这样三类：块元素，内联元素，内联块元素
		
## 块元素

	常见块元素：
		div,p,ul,ol,li,dl,dt,dd,form,table,tr,td,h1,h2,h3,h4,h5,h6,hr,fieldset

	块状元素特点：

	a) 块元素以块的形式显示为一个矩形区域
	b) 默认情况下，块元素独占一行，自上而下排列
	c) 块元素可以定义自己的宽度和高度，以及任意的margin，padding和border
	d) 块元素可以作为一个容器容纳其他的块元素和内联元素
	
## 内联元素（行内元素）

	常见内联元素：
		a,span,strong,b,em,i,label,br,img,input,textarea,select

	内联元素特点：
		a) 内联元素在一行逐个进行显示，也显示为一个矩形区域
		b) 内联元素不能定义自己的宽度和高度，宽高由内容撑开
		c) 内联元素可以设置左右padding和左右margin，设置与高度相关的属性不生效，例如margin-top,margin-bottom,padding-top,padding-bottom
		d) 内联元素只能嵌套内联元素，不能嵌套块元素

	常见内联块元素：
		img,input,select,textarea

	内联块元素特点：
		a) 即具有内联元素特点，在一行逐个进行显示
		b) 又具有块元素特点，可以设置宽高及任意margin,padding和border

	注：
		vertical-align属性只对这类型元素设置有效

	注：
		默认有margin或padding或border的元素

	body         默认margin
	h1-h6        默认margin
	p             默认margin
	ul，ol        默认margin和padding
	dl             默认margin
	dd              默认margin
	td              默认padding
	input          默认padding和border
	select        默认border
	option      默认padding
	textarea   默认padding和border
	
## 可变元素

	根据上下文关系决定元素类型
	
# 元素类型转换

	语法：
		display:block|inline|inline-block|none|list-item;
		
## display:block;

	将元素转换为块元素，是大部分块元素的默认display属性值
	
## display:inline;

	将元素转换为内联元素，是内联元素(如a,span等)的默认display属性值
	
## display:inline-block;

	将元素转换为内联块元素，是img，input这类型元素的默认display属性值
	
## display:none;

	将元素隐藏不可见

	Tip:
		overflow:hidden; 和display:none;的区别

		overflow:hidden;  是将元素的溢出部分隐藏不可见，没有溢出的部分正常显示
		display:none;  是将整个元素隐藏不可见
		
## display:list-item;

	将元素转换为列表类型，是li的默认display属性值

	注：
		当给内联元素设置float后，就相当于转换为了块元素，可以定义宽高及任意margin,padding,border属性
		
# 置换元素和非置换元素

## 置换元素

	浏览器根据元素的标签和属性，来决定元素的具体显示内容，例如:
		img标签的src属性值不同，决定了在网页中呈现的图片不同
		input标签的type属性值不同，决定了在网页中呈现的input控件类型不同
		
##非置换元素

	除了置换元素，大部分html元素都是非置换元素，其内容直接显示在浏览器中

	扩展：
		表单元素行高不一致，解决方案
		a) input{float:left;}
		b) input{vertical-align:middle;}
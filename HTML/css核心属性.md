# css核心属性

## 字体类属性

### 字体类型

	语法：
		font-family:字体1,字体2,字体3;

	eg: 
		body{font-family:"微软雅黑";}

	注：
		a)font-family设置多个字体时，多个字体之间用逗号分隔
		b)中文字体要加双引号，英文字体如果由多个单词组成也要加双引号
		c)特殊字体一律用图片
		d)设置多个字体时，浏览器会优先识别字体1，如果无法识别，识别字体2，如果列出的所有字体都无法识别，显示浏览器默认字体
		e)windows系统默认字体为宋体或新宋体，新推出版本为微软雅黑
		
### 字体大小

	语法： 
		font-size:数值+单位;

	eg:  
		p{font-size:14px;}

	注:
		a) 字体大小一般设置偶数不设置奇数
		b) 浏览器默认字体大小为16px
		c) 常见的字体大小的单位有px，em，rem
		d) font-size:medium;  等价于  font-size:16px;   等价于  font-size:1em;
		
### 字体加粗

	语法：
		font-weight:normal(常规字体)|bold(加粗)|bolder(加粗)|100-900；

	eg:  
		h1,h2,h3,h4,h5,h6{font-weight:100-500|normal;}

	注：
		当设置为数值时，100-500为常规字体，600-900为加粗字体
		
### 字体倾斜

	语法：
		font-style:normal(常规字体)|italic(倾斜)|oblique(倾斜)；

	eg:  
		em,i{font-style:normal;}
		
### 字体是否大写

	语法：
		font-variant:normal(常规字体)|small-caps(小型大写字母字体);

	注：
		只对英文起作用
		
### font复合写法

	语法： 
		font: style weight  size   family;

	eg: 
		font:italic bcoold 18px  "微软雅黑";

	注：
	a) font复合写法中，font-size和font-family不能和其他属性互换位置，必须放在最后
    b) font-size和font-family也不能互换位置，必须先写size，再写family
    c) font:12px/1.5 "黑体";   这句话表示字体大小为12px，行高为字体大小的1.5倍，字体类型为黑体
	
### 字体颜色

	语法：
		color:颜色值;

	注：
	颜色值的三种设置方式：

	a) 十六进制写法
		color:#000; (黑色)       color:#fff; （白色）
	b) rgb模式写法
		color:rgb(0,0,0);  （黑色）   color:rgb(255,255,255);   （白色）
	c) 颜色值单词
		color:red;   color:blue;  color:black;
		
## 文本类属性

### 水平对齐方式

	语法：
		text-align:left|center|right|justify;

	left:左对齐      
	center:居中对齐
	right：右对齐
	justify：两端对齐（只对英文起作用）
	
### 行高

	语法：
		line-height:normal(默认值)|数值+单位;

	eg: 
		p{line-height:35px;}

	注：
	a) line-height属性值只写数值不加单位时，代表行高为字体大小的多少倍
    b) 当行高等于容器高时，可以实现单行文本在定高
    c) line-height不允许设置负值
	
### 文本修饰

	语法：
		text-decoration:none(去掉文本修饰)|underline(下划线)|overline(上划线)|line-through(删除线);

	eg:  
		a{text-decoration:none;}  a:hover{text-decoration:underline;}
		
### 首行缩进

	语法：
		text-indent:数值+单位;

	eg:  
		p{text-indent:24px;}

	注：
		正值向后缩进，负值向前缩进，当给较大负值时，会有类似于隐藏的效果
		
### 字符间距

	语法： 
		letter-spacing:数值+单位;

	注：
		主要用来设置中文汉字和汉字之间的距离，英文字母与字母之间的距离，允许设置负值
		
### 词间距

	语法： 
		word-spacing:数值+单位；

	注：
		此属性只对英文起作用，主要用来设置英文单词和单词之间的距离，允许设置负值
		
### 文本是否大小写

	语法：
		text-transform:none(默认值)|capitalize(首字母大写)|uppercase(全部大写)|lowercase(全部小写);
		
### 长单词换行

	语法：
		word-wrap:normal(默认值)|break-word;

	注：
		该属性主要用于长单词换行和较长的url地址换行
		
### 强制在一行显示

	语法： 
		white-space:nowrap|normal(默认值);
		
### 标准文档流
	所谓的文档流指的就是元素(标签)排版(浏览器解析的时候)，顺序是从上向下 从左向右

	标准文档流微观现象：
		a:空白折叠
		b:高矮不齐，底边对齐
		c:自动换行 一行写不满就换行写  

	标准文档流中的元素等级问题：
	块级元素和行内元素

	行内元素的特性:
		a: 没有办法设置宽度和高度，宽度和高度只能凭借内容去撑起来，如果行内元素当中没有内容的话，就会缩成一小条。
		b: 多个行内元素可以并排显示
	块级元素的特性:
		a: 可以设置宽度和高度
		b: 如果一个块级元素没有设置宽度，那么这个块级元素宽度就会默认占满当前屏幕宽度的百分百。
		c: 块级元素不能和其他元素并排显示

	常用的块级元素标签:
		div p h1-h6  列表 ul li ol li dl dt dd 
	常用的行内元素标签:
		b  span em i u s a

	行内元素与块级元素相互转换  -- display 
	如果想要把行内元素转换成块级元素 display:block;
	如果想要把块级元素转换成行内元素  display:inline;
	display:inline-block; 转换成行内块元素 (特性：既可以设置宽高又可以并排显示)
	
### 文本流控制

	语法：
		layout-flow:horizontal(从左到右)|vertical-ideographic(从上到下);

	注：
		只有IE浏览器支持
		
### 垂直对齐方式

	语法：
		vertical-align:baseline(默认值)|top(顶部对齐)|middle(中部对齐)|bottom(底部对齐);

	注：
		(1)此属性可设置table单元格框中的内容的垂直对齐方式    
		(2)该属性定义行内元素的基线相对于该元素所在行的基线的垂直对齐
		
## 列表类属性

### 列表符号类型

	语法：
		list-style-type:disc(实心圆)|circle(空心圆)|square(实心方块)|decimal(数字)|none(去掉列表符号样式);

### 使用图片作为列表符号

	语法：
		list-style-image:url(图片路径);
		
### 设置列表符号的位置

	语法： 
		list-style-position:outside(外)|inside(里);
		
### list-style简写方式

	语法：
		list-style:类型  图片  位置;

	eg:
		ul,ol{list-style:none;}  或  li{list-style:none;}  去掉列表符号
		
## 背景类属性

### 背景色

	语法：
		background-color:颜色值;

	注：
		属性值的设置方法同color
		
### 背景图

	语法：
		background-image:url(图片路径);

	注：
		在网页中有两种图片表现形式：插入图片和背景图
		a) 插入图片		数据型图片，需要频繁更换的图片，使用img标签引入
		b) 背景图		用来装饰网页的图片使用背景图，我们可以在背景图上显示其他的文字内容和图片
	注: 
		背景图的三种显示原则
		a) 当背景图尺寸等于容器尺寸时，背景图恰好显示在容器中
		b) 当背景图尺寸小于容器尺寸时，背景图默认平铺直至铺满整个容器
		c) 当背景图尺寸大于容器尺寸时，只能显示容器范围以内的背景图
		
### 背景平铺属性

	语法:
		background-repeat:repeat(平铺)|repeat-x(横向平铺)|repeat-y(纵向平铺)|no-repeat(不平铺);
		
### 背景图位置

	语法
		：background-position:left|center|right|数值    top|center|bottom|数值;

	注：
		a）background-position的属性值有两个值，第一个值代表水平方向，第二个值代表垂直方向
		b）当设置为数值时，水平方向向右为正，向左为负，垂直方向向下为正，向上为负
		c）当两个值都为center时，可以省略第二个值
		
### background属性简写方式

	语法：
		background:背景色  背景图  背景平铺  背景图位置;

	eg: 
		background:blue url(img/1.jpg)  no-repeat right bottom;
		
### 背景图固定

	语法：
		background-attachment:scroll|fixed(固定);

	注：
		该属性用来设置当出现滚动条时，背景图固定不跟随滚动条滚动

	扩展：
		网页中常见的三种图片格式
		a）jpg：有损压缩格式，靠损失图片本身的质量来减小图片体积，适用于色彩丰富的图像
		b）gif：有损压缩格式，靠损失图片的色彩数量来减小图片体积，适用于颜色较少的图像。（支持动画，支持透明）
		c）png：有损压缩格式，----------------------------------------，适用于颜色-----------（支持透明）
	
## 浮动
	html网页中对于元素的种种限制，其实都来自于标准文档流，例如行内元素不能设置宽度和高度，块级元素不能并排显示等等，那么想要摆脱这些限制，那么就需要"脱离标准文档流".

	脱离标准文档流的方法有三种:
		浮动
		绝对定位
		浮动：
		float: 浮动
			值: left/right;

	浮动的标准特性:
		1.让元素脱离标准文档流
		2. 浮动会让元素相互紧贴
		3. 会存在字围效果
		4. 收缩效果

	浮动元素带来的影响解决方案:
		1. 给父元素(必须是子元素发生了浮动)设置一个具体的高度
		2. 使用clear:both属性 
		3. 使用:after :before(伪类)来实现。固定定位
		
	语法：
		float:none(默认值，不浮动)|left(左浮动)|right(右浮动);

	作用： 
		a）设置float属性可以让某些元素脱离默认文档流，在一行显示，
        b） 还可以通过左浮动和右浮动实现一个在左，一个在右的效果
	
# css基础

## css概念及特点

css—Cascading Style Sheets （层叠样式表）：

​	特点：

​		很好的实现了结构与表现相分离，降低了服务器成本，控制了页面布局，提高了页面加载速度

​	作用：

​		规定html元素如何在浏览器中呈现

## css语法

css由选择符和声明两大部分组成，声明又是有属性和属性值组成。即：

	选择符{属性:属性值;}

	eg:  
		h1{color:red;}

	Tip： 
		a) 声明要放在花括号中，建议每条声明占一行，每条声明结束要加分号
        b) 属性和属性值用冒号连接
        c) 所有的标点符号都必须是英文状态下的
		
## 样式表的创建

### 内联样式（行间样式或行内样式）

	语法：
		<标记 style="属性:属性值;"></标记>

	eg:  
		<h1 style="color:red;">千锋教育</h1>

### 内部样式表（嵌入式样式）语法：<style type="text/css">

    选择符{
          属性:属性值;
        }
		</style>
	eg: 
		<style type="text/css">
			h1{
				color:red;
			}
		</style>

	Tip：
		style标记一般放置在head部分
		
### 外部样式表

	a) 使用link引入

	语法：
		首先创建一个后缀名为.css的文件，然后在html页面使用link标签引入，即：
		<link rel="stylesheet" type="text/css" href="css文件路径"/>

	Tip： 
		rel的作用：表明引入文件与当前文件的关系
        link标签一般也放在head部分

	b) 使用@import引入

	语法： 
		@import   "css文件路径";
		

	注：
	link和@import引入外部样式的区别：
	1) link是html标签，除了可以引入css文件外，还可以引入其他文件，@import属于css的范畴，只能引入css文件
		（老祖宗的区别）
	2)link引入的css文件和页面同时加载，@import引入的css文件在页面加载完成后载入（加载顺序不同）
	3)link是html标签，无兼容性问题，@import是css2.1提出的，低版本浏览器不支持（浏览器支持不同）
	4)link是html标签，支持js控制DOM改变样式，@import不支持 （是否支持js改变DOM）
	
### 样式表的优先级（三种样式表的区别）

	采取就近原则，即离被设置的元素越近，优先级越高，一般情况下：
		内联>内部>外部

	注：
		当css属性值中出现!important关键词时，它的优先级最高

	即： 
		!important>内联>内部>外部



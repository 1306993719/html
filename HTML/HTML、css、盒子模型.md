# HTML

# WEB标准，W3C/WHATWG/ECMA相关概念

### WEB标准组成 

####组织解析：

（1）W3C( World Wide Web Consortium )万维网联盟，创建于1994年是Web技术领域最具权威和影响力的国际中立性技术标准机构。
**W3C (制定了结构(xhtml、xml)和表现(css)的标准，非赢利性的。)**
（2）ECMA(European Computer Manufactures Association) 欧洲电脑场商联合会。
**ECMA制定了行为(DOM(文档对象模型)，ECMAScript)标准**

（3）WHATWG网页超文本应用技术工作小组是：

一个以推动网络HTML 5 标准为目的而成立的组织。在2004年，由Opera、Mozilla基金会和苹果这些浏览器厂商组成。

####HTML及相关概念的介绍

**HTML 指的是超文本标记语言 (Hyper Text Markup Language) www万维网的描述性语言。**

XHTML指可扩展超文本标记语言（标识语言）（EXtensible HyperText Markup Language）是一种置标语言，表现方式与超文本标记语言（HTML）类似，不过语法上更加严格。

HTML5指的是HTML的第五次重大修改（第5个版本）(HTML5 是 W3C 与 WHATWG 合作的结果)

###HTML发展历史

![img](file:///C:/Users/Administrator/Desktop/%E8%80%81%E5%B8%88%E8%AF%BE%E4%BB%B6/%E4%B8%80%E9%98%B6%E6%AE%B5%E6%8E%88%E8%AF%BE/%E7%AC%AC%E4%B8%80%E5%91%A8%E5%86%85%E5%AE%B9/day01/%E8%B5%84%E6%96%99/images/pic03.png) 

# 相关软件的应用以及站点的创建

**1)****站点的作用**
A/ 用来归纳一个网站上所有的网页、素材以及他们之间的联系
B/ 规划网站的所有内容和代码 整合资源
**2)****创建站点的步骤**
创建网页所需各个文件夹 css、js、images
**3)文件的命名规则**
A/ 件命名规则：用英文，不用中文
B/ 名称全部用小写英文字母、数字、下划线的组合，其中不得包含汉字、空格和特殊字符；必须以英文字母开头。
C/ 网站的首页必须命名为index.html不建议使用shouye.html

# HTML基本结构和HTML基本语法

## HTML基本结构

![img](file:///C:/Users/Administrator/Desktop/%E8%80%81%E5%B8%88%E8%AF%BE%E4%BB%B6/%E4%B8%80%E9%98%B6%E6%AE%B5%E6%8E%88%E8%AF%BE/%E7%AC%AC%E4%B8%80%E5%91%A8%E5%86%85%E5%AE%B9/day01/%E8%B5%84%E6%96%99/images/pic06.png) 

## HTML的基本语法

### <常规标记>

<标记 属性=“属性值” 属性=“属性值”></标记>

标记也可叫标签或叫元素
例如：<head></head>v

### 空标记

<标记 属性=“属性值” />
例如：<meta charset=”utf-8”>

**说明：**
1.写在<>中的第一个单词叫做标记，标签，元素。
2.标记和属性用空格隔开，属性和属性值用等号连接，属性值必须放在“”号内。
3.一个标记可以没有属性也可以有多个属性，属性和属性之间不分先后顺序。
4.空标记没有结束标签，用“/”代替。

# HTML常用标记

### 文本标题（h1-h6）  

<h1>LOGO</h1> 
<h2>二级标题</h2> 
<h3>三级标题H3</h3> 
<h4>四级标题H4</h4> 
<h5>五级标题</h5>
<h6>六级标题</h6>

注：文本标题标签自带加粗，有自己的文本大小，并且独占一行，有默认间距

### 段落文本(p)  

<p>段落文本内容</p>
标识一个段落(段落与段落之间有段间距)

### 空格 

**&nbsp**
所占位置没有一个确定的值,这与当前字体字号都有关系.

### 换行(br)

<br />
换行是一个空标记(强制换行)

### 水平线

 <hr />空标记

### 加粗有两个标记

A、<b>加粗内容</b>只是显示加粗
B、<strong>强调的内容</strong>突出的文本

### 倾斜

<em>强调文本</em>

<i>倾斜文本</i>

####倾斜扩展

####<u>文本</u>下划线

<del>文本</del>删除线

<s>文本</s>删除线

<sub></sub>下标

<sup></sup>上标

### 列表(ul,ol,dl)

HTML中有三种列表分别是：无序列表，有序列表，自定义列表
*无序列表

####无序列表组成：

<ul>(unordered list)
<li></li>
<li></li>
．．．．．．
</ul>

####*有序列表

有序列表组成：
<ol>(ordered list)
<li></li>
<li></li>
．．．．．．
</ol>

####*自定义列表

<dl>(definition list)
<dt>名词</dt>
<dd>解释</dd>
(definition description)
．．．．．．
</dl>

####扩展2----有序列表的属性

1)、type:规定列表中的列表项目的项目符号的类型
语法：<ol type="a"></ol>
**1** **数字顺序的有序列表**（默认值）（1, 2, 3, 4）。
**a 字母顺序的有序列表**，小写（a, b, c, d）。
**A 字母顺序的有序列表**，大写（A,B,C,D)
**i 罗马数字**，小写（i, ii, iii, iv）。
**I 罗马数字**，大写（I, ii, iii, iv）。
2)、start 属性规定有序列表的开始点。
语法：<ol start="5"></ol>

### 插入图片

```html
<img src="目标文件路径及全称" alt="图片替换文本" title="图片标题" width="宽度" height="高度"/>
注:所要插入的图片必须放在站点下
title的作用:图片的标题； 在你鼠标悬停在该图片上时显示一个小提示，鼠标离开就没有了，HTML的绝大多数标签都支持title属性，title属性就是专门做提示信息的
alt的作用:提示文本 必写；alt属性是在你的图片因为某种原因不能加载时在页面显示的提示信息，它会直接输出在原本加载图片的地方。（优化图片的）

```

##绝对路径和相对路径

**相对路径**是指从发问者得角度去说明位置

**绝对路径**是从根源位置开始阐述。

####相对路径的写法：

1)当当前文件与目标文件在同一目录下，直接书写目标文件文件名+扩展名；<img src=”q12.jpg”/>
2)当当前文件与目标文件所处的文件夹在同一目录下，写法如下：
文件夹名/目标文件全称+扩展名；<img src=”images/q12.jpg”/>
3)当当前文件所处的文件夹和目标文件所处的文件夹在同一目录下，写法如下：
../目标文件所处文件夹名/目标文件文件名+扩展名；
<img src=”../images/q12.jpg”/>



### 超链接的应用

```html
语法：
<a href="目标文件路径及全称/连接地址" title="提示文本">链接文本/图片</a>
<a href="#"></a>空链接
属性：target:页面打开方式，默认属性值_self。
属性值：_blank 新窗口打开
<a href="#" target="_blank">新页面打开</a>
```

### 数据表格的作用及组成

```html
作用：显示数据
表格组成
<table width="value" height="value" border="value">
      <tr>
            <td></td>
            <td></td>
     </tr>
</table>

注：一个tr表示一行;一个td表示一列(一个单元格)

<th></th>表格的列标题
*数据表格的相关属性
1）width="表格的宽度"
2）height="表格的高度"
3）border="表格的边框"
4）bgcolor="表格的背景色"
5）bordercolor="表格的边框颜色"
6）cellspacing="单元格与单元格之间的间距"
7）cellpadding="单元格与内容之间的空隙"
8）水平对齐方式：align="left左对齐/center居中/right右对齐";

9) 垂直对齐方式 ：valign="top顶对齐/middle居中/bottom底对齐/baseline(基线);
10)合并单元格属性：
colspan=“所要合并的单元格的列数"合并列;

rowspan=“所要合并单元格的行数”合并行;
```

###合并单元格属性：

####colspan=“所要合并的单元格的列数"合并列;

####rowspan=“所要合并单元格的行数”合并行;



### 表单的作用及组成

**表单的作用**：用来**收集用户的信息**的;

表单组成：表单框（表单域form）

                  提示信息
    
                 表单控件/表单元素

#####1)、表单框

<form name="表单名称（英文字母开头的）" method（提交方式）="post/get" action="表单提交的地址"></form>

####Form中的获取数据的两个方式get和post的区别？

```html
1. get是从服务器上获取数据，post是向服务器传送数据。
2. get是把参数数据队列加到提交表单的ACTION属性所指的URL中，值和表单内各个字段一一对应，在URL中可以看到。post是通过HTTP post机制，将表单内各个字段与其内容放置在HTML HEADER内一起传送到ACTION属性所指的URL地址。用户看不到这个过程。
3. 对于get方式，服务器端用Request.QueryString获取变量的值，对于post方式，服务器端用Request.Form获取提交的数据。
4. get传送的数据量较小，不能大于2KB。post传送的数据量较大，一般被默认为不受限制。
5. get安全性非常低，post安全性较高。但是执行效率却比Post方法好。
建议：
1、get方式的安全性较Post方式要差些，包含机密信息的话，建议用Post数据提交方式；

2、在做数据查询时，建议用Get方式；而在做数据添加、修改或删除时，建议用Post方式；
```

#####2）文本框

<input type="text" value="默认值" placeholder="提示文本" />

#####3)密码框

<input type="password" placeholder="密码"/>

#####4)提交按钮

<input type="submit" value="按钮内容" />

<input type="reset" value="按钮内容"/>重置按钮 

#####5）单选框/单选按钮

<input type="radio" name="ral" value="radiovalue"/>
<input type="radio" name="ral" checked="checked" />
单选按钮里的name属性必须写，同一组单选按钮的name属性值必须一样。

#####6）复选框

<input type="checkbox" name="like" value="checkboxvalue" />

复选按钮里的name属性必须写，同一组复选按钮的name属性值必须一样。

checked="checked"表示默认被选中，可简写成**checked**

disabled="disabled"表示禁用，可简写成**disabled**

**enabled:可用状态**

#####7)下拉菜单

<select name="">
<option name="" value="表单被提交时被发送到服务器的值">菜单内容</option>
</select>

#####8）多行文本框（文本域）

<textarea name="textareal" cols="字符宽度" rows="行数">
</textarea>

#####9)跳转按钮

<input name="'" type="button" value=“按钮内容” />
<button></button>

#####button和submit的区别是：

submit是提交按钮起到提交信息的作用，type类型是button只起到跳转的作用，不进行提交。
提示信息标签(作用：将提示信息及相应的表单控件进行关联)

<label   for="user">提示信息</label>

<input type="text" id="user"/>

### 扩展知识点3：对于不同的输入类型，value 属性的用法的意义

```html
value 属性为 input 元素设定值。
对于不同的输入类型，value 属性的用法也不同：
type="button", "reset", "submit" - 定义按钮上的显示的文本
type="text", "password" - 定义输入字段的初始值
type="checkbox", "radio" - 定义与输入相关联的值
注释：<input type="checkbox"> 和 <input type="radio"> 中必须设置 value 他name属性。
扩展知识点4：

<form name="表单名称" method="post/get" action=""></form>
```

### 

```html

```

###div和span的用法

<div ></div>

没有具体含义， 除了独占一行之外没有任何其它的默认属性，是页面布局中常用的标签；
<span> </span>
文本结点标签
可以是某一小段文本，或是某一个字。 它除了不换行外，没有任何其它的默认属性； 

# 盒子模型 

##包含有:width height padding border margin 

一切标签都可以看成是盒子

###A:width 和 height 

宽度和高度与正常人类的看法是有区别的。我们前端程序员说的宽度和高度实际上指的是内容的宽度和高度

###B: border: 边框 

border:1px solid red; 

1px 表示边框的宽度  
solid 表示边框的线型
red 边框的颜色 

###C: padding 

padding是内容与边框之间的距离 ，我们称它为内边距。  
padding有四个方向，我们可以采用简写:
padding:10px;  上右下左四个方向的padding都为10px
padding:10px 20px; 上下10 左右20
padding:10px 20px 30px ; 上10 左右20 下30 
padding:10px 20px 30px 40px; 上10 右20 下30 左40

单独某个方向设置值：
padding-top
padding-right
padding-bottom
padding-left 

可以进行padding覆盖
padding:10px;
padding-left:20px;

Tip:padding使用后会增加盒子实际所占的宽度和高度，如果不想改变盒子原本所占有的宽度和高度，那么就把宽度和高度减少(内容的宽度和高度)

###D.margin - 外边距

margin:10px; 上右下左 都是10px
margin:10px 20px; 上下 左右
margin:10px 20px 30px; 上 左右 下 
margin:10px 20px 30px 40px; 上右下左 

####margin塌陷 

 (此种情况只发生在标准文档流当中，一旦元素脱离了标准文档流那么也就不存在所谓的塌陷)


margin值得设置： 既可以设置为具体的值也可以设置为auto。

####margin让元素居中:

​	**margin:0 auto;**
	想要通过margin:0 auto;让元素居中显示，需要注意下面的几点(一定一定一定要记住)：

		1. 想要使用margin：0 auto；必须要有宽度width,明确的width
		2. 只有在标准文档流当中的盒子才能使用。一旦元素设置了浮动、绝对定位、固定定位，那么就不能使用margin:0 auto;居中
		3. margin:0 auto;只是让盒子居中，至于说盒子里面的文本内容想要居中，请使用text-align:center;
		text-align:left / center /right;


# 标准文档流



所谓的文档流指的就是元素(标签)排版(浏览器解析的时候)，顺序是从上向下 从左向右

##标准文档流微观现象：

###a:空白折叠

###b:高矮不齐，底边对齐

### c:自动换行 一行写不满就换行写  



##块级元素和行内元素

标准文档流中的元素等级问题：

####行内元素的特性:

​	a: 没有办法设置宽度和高度，宽度和高度只能凭借内容去撑起来，如果行内元素当中没有内容的话，就会缩成一小条。
	b: 多个行内元素可以并排显示
块级元素的特性:
	a: 可以设置宽度和高度
	b: 如果一个块级元素没有设置宽度，那么这个块级元素宽度就会默认占满当前屏幕宽度的百分百。
	c: 块级元素不能和其他元素并排显示

#### display

行内元素与块级元素相互转换  -- display

#### display:block

如果想要把行内元素转换成块级元素 display:block;

#### display:inline

如果想要把块级元素转换成行内元素  display:inline;

#### display:inline-block

display:inline-block; 转换成行内块元素 (特性：既可以设置宽高又可以并排显示)

##常用的块级元素标签:

​	div p h1-h6  列表 ul li ol li dl dt dd 

##常用的行内元素标签:

​	b  span em i u s a




# CSS简介



##css:层叠样式表 

英文全名：cascading style sheets ,WEB标准中的表现标准语言,表现标准语言在网页中主要对网页信息的显示进行控制，简单说就是如何修饰网页信息的显示样式。

 目前推荐遵循的是W3C发布的CSS3.0. 用来修饰XHTML或者XML等样式文件的计算机语言。 1998年5月21日由w3C正式推出的css2.0 

##css语法

CSS语法：选择符{属性：属性值；属性：属性值；} 

![img](file:///C:/Users/Administrator/Desktop/%E8%80%81%E5%B8%88%E8%AF%BE%E4%BB%B6/%E4%B8%80%E9%98%B6%E6%AE%B5%E6%8E%88%E8%AF%BE/%E7%AC%AC%E4%B8%80%E5%91%A8%E5%86%85%E5%AE%B9/day04/%E8%B5%84%E6%96%99/02/images/pic1.png) 

选择符表示要定义样式的对象，可以是元素本身，也可以是一类元素或者制定名称的元素.

属性：属性是指定元素所具有的属性，它是css的核心，css2共有150多个属性

属性值：属性值包括法定属性值及常见的数值加单位，如25px，或颜色值等。

说明： 

1）每个CSS样式由两部分组成，即选择符和声明，声明又分为属性和属性值； 

2）属性必须放在花括号中，属性与属性值用冒号连接。

 3）每条声明用分号结束。 

4）当一个属性有多个属性值的时候，属性值与属性值不分先后顺序。 5）在书写样式过程中，空格、换行等操作不影响属性显示。 

##样式的创建

样式的创建（内部样式表 外部样式表 内联样式表）

###A. **内部样式表**

<style>.......</style>

写在标记<head></head>中。

###B.**外部样式**

**外部样式的创建**

<link rel="stylesheet" type="text/css"  href="目标文件的路径及文件名称”

**外部样式标的导入**

<style>

@import url(目标文件的路径及文件名全称)

</style>

###C.**内联样式**

**（行间样式，行内样式，嵌入式样式，内嵌样式）**

<标签 style=“属性：属性值；属性：属性值；”>  </标签>

例子：<div style="width:500px;  height:200px;"> </div>

###**样式表的优先级**

a. **内联**样式表的优先级**最高**

b.内部样式表与外部样式表的优先级和书写顺序有关，**后书写的优先级最高**

c.作用域：**内联样式的作用域最小**，只能用于当前元素，其次是内部样式表，能应用于当前HTML文件，最后是内部样式表，能应用于所有链接的HTML文件。

#**伪类选择器**

a:link{属性：属性值;}超链接的初始状态; 

a:visited{属性：属性值;}超链接被访问后的状态; 

a:hover{属性：属性值;}鼠标悬停，即鼠标划过超链接时的状态; 

a:active{属性：属性值;}超链接被激活时的状态，即鼠标按下时超链接的状态; 

**Link--visited--hover--active。** 必须按顺序写

**a:link,  a:visited,  a:hover,   a:active** 

##两种引入外部样式表link和import之间的区别

link和import导入外部样式的区别：

> **差别1：本质的差别：**link属于XHTML标签，而@import完全是CSS提供的一种方式。
>
> **差别2：加载顺序的差别：**当一个页面被加载的时候（就是被浏览者浏览的时候），link引用的CSS会同时被加载，而@import引用的CSS会等到页面全部被下载完再被加载。所以有时候浏览@import加载CSS的页面时开始会没有样式（就是闪烁），网速慢的时候还挺明显。
> **差别3：兼容性的差别：**@import是CSS2.1提出的，所以老的浏览器不支持，@import只有在IE5以上的才能识别，而link标签无此问题。
> **差别4：使用dom(document object model文档对象模型 )控制样式时的差别**：当使用javascript控制dom去改变样式的时候，只能使用link标签，因为@import不是dom可以控制的.

## 样式表的优先级

A、内联样式表的优先级别最高
B、内部样式表与外部样式表的优先级和书写的顺序有关，后书写的优先级别高。

C、作用域：内联样式的作用域最小，只能应用于当前元素，其次是内部样式表，能应用于当前HTML文件，最后是外部样式表，能应用于所有链接的HTML文件。



##三种基础选择器:

CSS选择符（选择器）:表示要定义样式的对象

###id选择器（最高）

> 语法：#id名{属性：属性值;}
> 说明：
> A）当我们使用id选择符时，应该为每个元素定义一个id属性
> 如：<div id="box"></div>
> B）id选择符的语法格式是“#”加上自定义的id名
> 如：#box{width:300px; height:300px;}
>
> C) 起名时要取英文名，不能用关键字：(所有的标记和属性都是关键字)
> 如：head标记
> D）一个id名称只能对应文档中一个具体的元素对象，因为id只能定义页面中某一个唯一的元素对象。
> E) 最大的用处：创建网页的外围结构。

###class选择器/类选择器（其次）

> 语法：·class名{属性：属性值;}
> 说明：
> A）当我们使用class选择符时，应先为每个元素定义一个class名称
> B）class选择符的语法格式是：
>
> "如：<div class="top"></div>"
>
> .top{width:200px; height:100px; background:green;}
> 用法：class选择符更适合定义一类样式；

###div标签选择器（最后）

 

> 语法：选择符1，选择符2，选择符3{属性：属性值;} 例：#top1,#nav1{width:960px;}
> 说明：当有多个选择符应用相同的样式时，可以将选择符用“，”分隔的方式，合并为一组。

##高级选择器:

​       1.* 通配符 全选

2. 后代选择器 div p    选择div后代当中所有的p标签
3. 子元素选择器 div>p 选择div的直系后代p
4. 交集选择器  span.d1  标签名叫span并且class叫做d1
5. 并集选择器  div,p,h1,h2,h3 同时选中当前的这些标签
6. 序列选择器 ul li:first-child ul li:last-child
7. 相邻兄弟选择器 div+p 选择挨着div的p
8. 普通兄弟选择器  div~p 选择div的兄弟元素p 

##CSS选择符的权重

css中用四位数字表示权重，权重(特殊性)的表达方式如：0，0，0，0
类型选择符（元素选择器）的权重为0001       如：div{width:100px; height:100px;}
class选择符的权重为0010       如：.box{width:100px; height:100px;}
id选择符的权重为0100

伪类选择符的权重为0010     如:a:link a:visited......

包含选择符的权重：为包含选择符的权重之和
子选择符的权重为0000

属性选择符的权重为0010
伪元素选择符的权重为0001 
内联样式的权重为1000
继承样式的权重为0000 

# 页面中的注释

##Html注释

<!-- 注释内容 -->

##css的注释

/* 我是css的注释 */



# css属性组成和作用

## css属性和属性值的定义

**属性**：属性是指定选择符所具有的属性，它是css的核心，css2共有150多个属性

**属性值**：属性值包括法定属性值及常见的数值加单位，如25px，或颜色值等。

## CSS文本属性

###文本大小：

{**font-size**:12px;}单位还可以是em，是父级元素的font-size的倍数；/系统默认的字号大小为16px

**说明：**

1） 属性值为数值型时，必须给属性值加单位，属性值为0时除外。

2）单位还可以是pt，9pt=12px;

3）为了减小系统间的字体显示差异，IE Netscape Mozilla的浏览器制作商于1999年召开会议，*共同确定16px/ppi为标准字体大小默认值,即1em.默认情况下，*1em=16px,0.75em=12px; rem

###文本字体：

{**font-family**:字体1，字体2，字体3；}

**说明：**

浏览器首先会寻找字体1、如存在就使用改字体来显示内容，如在字体1不存在的情况下，则会寻找字体2，如字体2也不存在，按字体3显示内容，如果字体3 也不存在；则按系统默认字体显示； 

当字体是中文字体时，需加双引号；

当英文字体由多个单词组成时，需加双引号如（“Times New Roman”）

当英文字体只有一个单词组成是不加双引号；如：（Arial）；

Windows中文版本操作系统下，中文默认字体为宋体或者新宋体，英文字体默认为Arial.

### 文字颜色

{**color**:颜色值;}red/#f00/rgb(255,0,0) 

```html
说明：

用十六进制(是计算机中数据的一种表示方法)表示颜色值：
0 1 2 3 4 5 6 7 8 9
0 1 2 3 4 5 6 7 8 9 A B C D E F
颜色模式：光色模式
R G B
FF 00 00
颜色值的缩写：
当表示三原色的三组数字同时相同时，可以缩写为三位;
当用十六进制表示颜色值时，需要在颜色值前加“#”
# fa 00 00
RGB表示方式：color:rgb(255,0,0);
```

###文字加粗

**font-weight**:bolder(更粗的)/bold（加粗）/normal（常规）/100—900; 

**说明：**

在css规范中，把字体的粗细分为9个等级，分别为100——900，其中100对应最轻的字体变形，而900对应最重的字体变形，

###文本倾斜：

**font-style**：italic/oblique/normal（取消倾斜，常规显示）; 

**说明：**

italic和oblique都是倾斜的文字, 但区别在于Italic是指斜体字，而Oblique是倾斜的文字，对于没有斜体的字体应该使用Oblique属性值来实现倾斜的文字效果.

###水平对齐方式

{**text-align**:left左/right右/center居中/justify两端对齐(在部分浏览器中，对于中文不起作用);} 只针对文本或图片

 ### 垂直对齐方式 

{**vertical-align**:top上/bottom下/middle居中/baseline基线（某些特定的元素类型起作用）;} 

### 文字行高 

{**line-height**:normal/value;}line-height:20px; line-height:2em; (当行高的单位省略时，默认为em)

**说明：**

当单行**文本的行高*等于*容器高**时，可实现单行文本在容器中***垂直方向居中对齐**；*
当单行文本的行高*小于*容器高时，可实现单行文本在容器中*垂直中齐以上；*
当单行文本的行高*大于*容器高时，可实现单行文本在容器中*垂直中齐以下*（IE6及以下版本存在浏览器兼容问题） 

###文本修饰 

**text-decoration:none**/underline/overline/line-through

**说明：**

none:没有修饰

underline:添加下划线

overline:添加上划线

line-through:添加删除线

###首行缩进：

{**text-indent**:value;}

**说明：**

1）text-indent可以取负值；

2）text-indent属性只对第一行起作用。

###检索英文字母大小写

{**text-transform**:none无转换/capitalize首字母大写/uppercase全都大写/lowercase全都小写;}。 

###字间距

{**letter-spacing**:value;}控制英文字母或汉字的字距。 

###词间距

{**word-spacing**:value;}控制英文单词词距。 

###文本流控制

{**layout-flow**:horizontal/vertical-ideographic;}

**说明：**

1）**horizontal:**自左向右

2）**vertical-ideographic**:自上而下

###文字属性简写：

**font**:bolder italic 12px/1.5em "宋体";     

简写时，字体和字号是必备font属性的简写：**字号，行高，字体** 

说明:font的属性值应按以下次序书写(各个属性之间用空格隔开) 

顺序: font-style font-weight font-size / line-height font-family

(1)简写时 , font-size和line-height只能通过斜杠/组成一个值，不能分开写。

(2) 这种简写法只有在同时指定font-size和font-family属性时才一起作用,如果你没有设定font-weight , font-style , 他们会使用缺省值。

# CSS列表属性



##定义列表符号样式

list-style-type：disc(实心圆)/circle(空心圆)/square(实心方块)/none(去掉列表符号)；

##使用图片作为列表符号

list-style-image：url(所使用图片的路径及全称)；

##定义列表符号的位置

list-style-position:outside(外边)/inside(里边)；

***list-style:none;****去掉列表符号***

# 边框的属性和属性值

border:边框宽度 边框风格 边框颜色;

例如：border:5px solid #ff0000

###边框宽度：border-width:

###边框颜色：border-color:

###边框样式：*border-style:*

***solid(实线)/dashed(虚线)**dotted(点划线)double(双线)*none(去掉边框);

###可单独设置一方向边框，

border-bottom:边框宽度 边框风格 边框颜色;      底边框

border-left:边框宽度 边框风格 边框颜色;             左边框

border-right:边框宽度 边框风格 边框颜色;          右边框

border-top:边框宽度 边框风格 边框颜色;           上边框

# CSS背景属性

##背景颜色 

{**background-color**:颜色值;}

##背景图片的设置

 **background-image**：url(背景图片的路径及全称）；

##背景图片平铺属

{**background-repeat**:no-repeat不平铺/repeat平铺/repeat-x  X轴平铺/repeat-y   Y轴平铺 }

##背景图的位置

**{background-position:left/center/right/数值      top/center/bottom/数值;}**

###水平方向上的对齐方式

**（left/center/right）或值** 

###垂直方向上的对齐方式

**(top/center/bottom)或值** 

###background-position:值1 值2; 

两个值 ：第一个值表示水平位置的值，第二个值：表示垂直的位置。 
当两个值都是center的时候写一个值就可以代表的是水平位置和垂直位置 ；

当元素小背景图大的时候，想显示右下方的背景图，通过负值来调整背景图的位置；

##背景图的固定

###background-attachmen

{background-attachment:fixed固定/scroll滚动;}

###fixed 

fixed 固定，不随内容一块滚动，根据可视窗口固定位置；

###scroll

scroll:随内容一块滚动。

####*网页上常用的图片格式*

1）**jpg** :有损压缩格式，靠损失图片本身的质量来减小图片的体积，适用于颜色丰富的图像;(像素点组成的，像素点越多会越清晰 )
2）**gif**：无损压缩格式，支持透明，支持动画，适用于颜色数量较少的图像;
3）**png**:无损压缩格式，支持透明，不支持动画，(是fireworks的 源文件格式)，适用于颜色数量较少的图像; 

# CSS浮动属性

##浮动的标准特性:

###1.让元素脱离标准文档流

###2. 浮动会让元素相互紧贴

###3. 会存在字围效果

###4. 收缩效果

##浮动元素带来的影响解决方案:

​	1. 给父元素(必须是子元素发生了浮动)设置一个具体的高度
	2. 使用clear:both属性 

   	3. 使用:after :before(伪类)来实现。
   	4. overflow:hidden
   	5. display不为none
   	6. 触发BFC

##*语法：float:none/left/right;*

浮动的**目的**：就是**让竖着的元素横着显示**

一个元素设置float：left/right;时，元素会脱离文档流（半脱离），不占空间；
有三个取值：

###left:元素向左浮动

###right:元素向右浮动

###none:默认值，不浮动。

![img](file:///C:/Users/Administrator/Desktop/%E8%80%81%E5%B8%88%E8%AF%BE%E4%BB%B6/%E4%B8%80%E9%98%B6%E6%AE%B5%E6%8E%88%E8%AF%BE/%E7%AC%AC%E4%B8%80%E5%91%A8%E5%86%85%E5%AE%B9/day03/%E8%B5%84%E6%96%99/%E7%AC%94%E8%AE%B0/float.jpg) 



*清除浮动可以理解为打破横向排列*。

###清除浮动的属性是clear，

语法：**clear : none | left | right | both**

####none

**none：默认值。**允许两边都可以有浮动对象

#### left

**left：清除左浮动**/不允许左边有浮动对象right

#### right

**right  :  清除右浮动**/不允许右边有浮动对象

#### both

**both  :  清除两端浮动**/不允许有浮动对象

有一点是要记住的那就是*

对于CSS的清除浮动(clear)，一定要牢记：这个规则**只能影响使用清除的元素本身，不能影响其他元素**


# 图像热区

## 含义

​	**在网页上进行了链接的一个区域。形象点说就是在网页上鼠标箭头变成小手的那个区域。 比如一个版面里面（落地页）表面上看上去是一张整体的图，但是实际上后台用切割的方式切割成一块一块的不同的链接区域，就称之为热区，如[中国地图)电子图中的一样，用热区分割成每一个区域，链接到每一个指定的地方。**

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>图像热区</title>
</head>
<body>
	<img src="images/01.jpg" alt="图像热区" usemap="#baofu">
	<map name="baofu" id="baofu">
		<area shape="poly" coords="100,20,400,20,300,20,450,400,340,700" href="" alt="">
	</map>
</body>
</html>
~~~

注： usemap属性值要等同于map标签的name值和id值，三者一定要完全相等
	如果三者没有完全相等 ，那么可能图像热区到了某些浏览器里就会失效。

## 图像热区的形状分类

###矩形（rect）

~~~html
 <area shape="rect" coords="0,0,200,200" href="http://www.baidu.com" alt=""> 
shape形状  coords坐标  href触发图像热区时会跳转的链接  alt图像失败时的提示
 坐标应该是矩形的左上角和右下角
~~~

### 圆形（circle）

~~~html
<area shape="circle" coords="100,100,50" href="http://www.hao123.com" alt="">
坐标应该是圆形的圆心坐标和半径
~~~

### 多边形（poly）

~~~html
<area shape="poly" coords="100,100,200,200,300,200,400,100" href="http://www.jd.com" alt=""> 
坐标应该是多边形每个定点的坐标
~~~



#	HTML5的发展史

​	HTML5草案的前身名为 Web Applications 1.0，于2004年被WHATWG提出，于2007年被W3C接纳，并成立了新的 HTML 工作团队。    **HTML 5 的第一份正式草案已于2008年1月22日公布**。HTML5 仍处于完善之中。然而，大部分现代浏览器已经具备了某些 HTML5 支持。    2012年12月17日，万维网联盟（W3C）正式宣布凝结了大量网络工作者心血的HTML5规范已经正式定稿。根据W3C的发言稿称：“HTML5是开放的Web网络平台的奠基石。”    **2013年5月6日， HTML 5.1正式草案公布**。该规范定义了第五次重大版本，第一次要修订万维网的核心语言：超文本标记语言（HTML）。在这个版本中，新功能不断推出，以帮助Web应用程序的作者，努力提高新元素互操作性，本次草案的发布，从2012年12月27日至今，进行了多达近百项的修改，包括HTML和XHTML的标签，相关的API、Canvas等，同时HTML5的图像img标签及svg也进行了改进，性能得到进一步提升。 

	### html5：广义来说是新一代的客户端后台解决方案，狭义来说是HTML第五代

### API：接口，功能对外开放的开关。

​	API（Application Programming Interface,[应用程序](http://baike.baidu.com/item/%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F)编程接口）是一些预先定义的[函数](http://baike.baidu.com/item/%E5%87%BD%E6%95%B0)，目的是提供[应用程序](http://baike.baidu.com/item/%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F)与开发人员基于某[软件](http://baike.baidu.com/item/%E8%BD%AF%E4%BB%B6)或硬件得以访问一组[例程](http://baike.baidu.com/item/%E4%BE%8B%E7%A8%8B)的能力，而又无需访问源码，或理解内部工作[机制](http://baike.baidu.com/item/%E6%9C%BA%E5%88%B6)的细节。

### 兼容性

​	**支持Html5的浏览器包括Firefox（火狐浏览器），IE9及其更高版本，Chrome（谷歌浏览器），Safari，Opera等；国内的 遨游浏览器（Maxthon），以及基于IE或Chromium（Chrome的工程版或称实验版）所推出的360浏览器、搜狗浏览器、QQ浏览器、猎豹浏览器等国产浏览器同样具备支持HTML5的能力。**

### HTML5 语法  

内容类型（ContentType）

​	  HTML5的文件扩展符与内容类型保持不变，仍然为".html"或".htm"。

DOCTYPE声明

  	<!DOCTYPE html>不区分大小写

​	指定字符集编码

```html
 <meta charset="UTF-8">
```

可省略结束标记的元素

 		允许不写结束标记的元素：br、col、embed、hr、img、input、、link、meta    

​                可以省略结束标记的元素：li、dt、dd、p、option、colgroup、thead、tbody、tfoot、tr、td、th

 		可以省略全部标记的元素：html、head、body、colgroup、tbody

省略引号

​		属性值可以使用双引号，也可以使用单引号。

### HTML5  新增语义化标签 

~~~html
section元素 
	表示页面中的一个内容区块
article元素 
	表示一块与上下文无关的独立的内容
aside元素
	是辅助article区域的内容。也可以理解为整个网页的辅助区域
header元素 
	表示页面中一个内容区块或整个页面的标题
footer元素 
	表示页面中一个内容区块或整个页面的脚注
nav元素 
	表示页面中导航链接部分
figure元素 
	表示一段独立的流内容，使用figcaption元素为其添加标题(第一个或最后一个子元素的位置)
 main元素 
	表示页面中的主要的内容(ie不兼容)
hgroup标题的一个分组
mark:标签定义带有记号的文本,在需要突出显示文本时使用 。兼容低版本浏览器：
	<script src=“html5.js”></script>
~~~



# video定义视频

~~~html
 <video src="movie.ogg" controls>Video元素</video> 
~~~

### 属性

  controls属性：如果出现该属性，则向用户显示控件，比如播放按钮。

  autoplay属性：如果出现该属性，则视频在就绪后马上播放。


  loop属性：重复播放属性。


  muted属性：静音属性。


  preload属性：页面加载时进行加载，并预备播放

  auto - 当页面加载后载入整个视频(全部预加载)

  metadata - 当页面加载后只载入元数据(部分预加载,（包括尺寸，第一帧，持续时间等等）


  none - 当页面加载后不载入视频(页面制作者认为用户不期望此视频，或者减少HTTP请求)

  poster属性：规定视频正在下载时显示的图像，直到用户点击播放按钮。

~~~html
<source   src=”路径”  type=”video/视频格式”> 标签为媒介元素（比如 <video> 和 <audio>）定义媒介资源。
Type属性值：
  用于视频：video/ogg   video/mp4     video/webm
~~~

### 代码举例



~~~html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>Index</title>
</head>
<body>
	<!-- 多媒体标签 -->
	<video controls autoplay loop muted>
		<!-- autoplay自动播放过程中需要配置muted属性 -->
		<source src="视频/3theB.mp4" type="video/mp4">
	</video>
	<audio  controls autoplay muted>
		<source src="视频/蔡健雅 - 被驯服的象.mp3" type="audio/mp3">
	</audio>
</body>
</html>
~~~

# audio定义音频（行内块元素）

~~~html
<audio src="">Audio元素</audio>
<source   src=”路径”  type=”video/视频格式”> 标签为媒介元素（比如 <video> 和 <audio>）定义媒介资源。
<source   src=”路径”  type=”audio/音频格式”>
Type属性值：
	用于音频：audio/ogg   audio/mpeg  (mp3)   wav
~~~

### 属性

  controls属性：如果出现该属性，则向用户显示控件，比如播放按钮。

  autoplay属性：如果出现该属性，则视频在就绪后马上播放。


  loop属性：重复播放属性。


  muted属性：静音属性。

### 兼容性

视频支持的格式 

![1553689830160](C:\Users\ADMINI~1\AppData\Local\Temp\1553689830160.png)

音频支持的格式

![1553689875631](C:\Users\ADMINI~1\AppData\Local\Temp\1553689875631.png)



# 智能表单

## 新增属性

**1.Type=“number” 专门用来输入数字的文本框**

Number：专门用来输入数字的文本框。在提交时会检查其中的内容是否为数字，具有min、max、step的属性。

 例：


~~~html
<input  name=“number1”  type=“number”  value=“25”  min=“10”  max=“100”  step=“5” >
~~~

**2.Type=“email”   限制用户必须输入email类型   ”@”**

**3.Type=“url”        限制用户必须输入url类型    ”http://”**

**4.Type=“range”   产生一个滑动条表单**

​	range：带有滑块控件的数字字段，它具有min属性与max属性，及step属性，可以指定每次拖动的步幅。

例：

~~~html
 <input  name=“range1” type=“range” value=“25” min=“0”  max=“100”  step=“5” >
 min最小值       max最大值       step 数字间隔

~~~

**5.Type=“search”   产生一个搜索意义的表单**

~~~html
<input type=”search” name=”name名”/>
~~~

**6.Type=“color”     生成一个颜色选择的表单**

**7.Type=“time”      限制用户必须输入时间类型**

**8.Type=“month”        限制用户必须输入月类型**

**9.Type=“week”        限制用户必须输入周类型**

**10.Type=“date”       显示有日期的日历控件**

**11.Type=“datetime-local”        选取本地时间**

**12.hidden ：输入类型定义隐藏字段。隐藏字段对于用户是不可见的。**

**13.output： 定义不同类型的输出，如计算结果的输出，或脚本的输出。**

​	注：必须从属于某个表单。即，必须将它书写在表单内部，Output标签IE不支持

例

~~~html
<form action="" oninput="all.value=parseInt(x.value)+parseInt(y.value)">
  <input id="x" type="range" min="0" max="100">100+
  <input id="y" type="text" value="50">=
  <output name="all" for="x y"></output>
</form>
~~~

**14.list属性**（结合datalist元素使用）**Datalist ：选项列表**  

例：

~~~html
<input type="url"   list="url_list"   name="link" />
<datalist    id="url_list"> 
<option label="W3School" value="http://www.W3School.com.cn" /> 
<option label="Google" value="http://www.google.com" /> 
<option label="Microsoft" value="http://www.microsoft.com" /> 
</datalist>
提示：option 元素永远都要设置 value 属性。
~~~

**15.placeholder属性：文本框处于未输入状态时文本框中显示的输入提示。**

例：

~~~html
<input type=”text” placeholder=”用户名”>当鼠标点击并输入内容后自动覆盖提示信息
~~~

**16.autofocus属性：给文本框、选择框、或者按钮控件加上该属性，当打开页面时，该控件自动获得焦点，一个页面只能有一个。**

**17.required属性：验证输入不能为空  写给你要验证的元素**例:input

**18.autocomplete属性：输入富足和所用的自动完成功能，是一个节省输入时间，同时也十分方便的功能。on/off/“”。on可是显示指定候补输入的数据列表，自动补全以前输入过的内容。**

~~~html
<input type="text"  autocomplete="on"  name ="greeting">
~~~

HTML5增加了大量在提交时对表单及表单元素内容有效性验证的功能。

**19.pattern**

​      将属性值设为某个格式的正则表达式，在提交时会检查其内容是否符合给定格式。    

例：

~~~html
<input type=”text”	 	pattern = “0-9{3}” 		title="输入内容：一个数与三个大写字母" 		placeholder=‘输入内容：一个数与三个大写字母’>
~~~

**20.取消验证novalidate属性**

  	可以对form表单添加**novalidate**属性，即使form表单中的input添加了required，也将不进行验证

**21.Multiple:可以输入一个或多个值，每个值之间用逗号分开，还可以应用于file** 

  例：

~~~html
<input type=“email” multiple>
~~~

##### 标签

分组：fieldset

分组的标题：legend

# CSS统筹

**整站里相同的CSS样式提取到一个样式表里，各个页面调用相同的样式文件即可**。

**网站较大的情况下一般会把网站的头部，尾部单独分离出来，包括样式文件。**

###  网页自身优化（如何让网站被搜索引擎搜索到）：

#### ★页面头部优化

​	页面头部指的是代码部分，具体一点就是指的“Description（描述）”和“Keywords（关键字）”两部分：

1、“描述”部分应该用近乎描述的语言写下一段介绍你网站的文字，在这其中，你应该适当的对你网站的特色内容加以重复以求突出；

2、“关键字”部分应该列出你认为合适的，能突出网站内容的关键字就可以了，关键字不要设置太多，可设置10---8个，搜索引擎只会浏览靠前的几个关键字。

~~~html
<meta name="keywords"   content="" >向搜索引擎说明你的网页的关键词； 
<meta name="description"    content="">告诉搜索引擎你的站点的主要内容；
~~~

#### ★超链接优化

搜索引擎为何可以能够索引全世界的网站，是因为各个搜索引擎程序中都有一个会自动“爬行”于互联网上的智能机器人程序，这个机器人就是顺着网站之间的链接游览世界的，那么我们就应该为它创造一个良好的爬行通道——合理的设置链接。 怎样的链接才是合理的呢？

​	1、采用纯文本链接，少用，最好是别用Flash动画设置链接	

​	因为搜索引擎无法识别Flash上的文字.许多公司、个人都喜欢酷酷的Flash动画，网站的入口也做成Flash片断，，搜索引擎很难光顾这样的网站。而且个别设计者非常马虎，把网站的入口链接放在了Flash上，有时因为网络繁忙、缺少Flash插件而导致用户根本就看不到网站的内容，

​	2、按规范书写超链接，这个title属性，它既可以起到提示访客的作用，也可以让搜索引擎知道它要去哪里.

​	3、最好别使用图片热点链接，理由和第一点差不多。

~~~html 
<a href="id名"></a>
~~~

#### ★图片优化(alt属性，title属性)

图片优化并不是修改图片的大小、颜色，而是你应该为每个标签加上alt属性，alt属性的作用是当图片无法显示时以文字作为替代显示出来，而对于SEO来说，它可以令搜索引擎有机会索引你网站上的图片，对于一些确实没什么意义的图片，最好也不要省略alt，而应该留空，即 alt=""。

#### ★避免大“体积”的页面

有经验表明，搜索引擎不喜欢索引大体积的页面，即一个页面代码部分的体积不要太大，控制在100kb内为佳.

#### ★最重要的一点！合理的代码结构

搜索引擎喜欢格式清晰，结构分明的页面，理论上XML是最合乎搜索引擎，当然，这太极端了，不过如果采用XHTML+CSS技术将页面数据同表现分离，即避免大量嵌套表格和其它冗余的代码还是能够完美实现这一要求的。

**原则：简化代码，易修改**

# CSS规范

## 1、命名方法（语义化命名，结构化命名）

ID:结构化   head   

class: .border0    . red:    .font12      .clear

## 2、CSS命名规则

1）建议使用小写字母

2）以英文字母开头，后面可以连接数字、字母、下划线、连字符，建议尽量使用英文字母，适当使用下划线和连接线；

3）词必达意，名称要反映用途和相关信息，同时也要简短。

# CSS Reset样式重置

**现象**

在HTML标签在浏览器里有默认的样式，例如 p 标签有上下边距，strong标签有字体加粗样式，em标签有字体倾斜样式。不同浏览器的默认样式之间也会有差别，例缩进的样式，在IE下，它的缩进是通过margin实现的，而Firefox下，它的缩进是由padding实现的。在切换页面的时候，浏览器的默认样式往往会给我们带来麻烦，影响开发效率。所以解决的方法就是一开始就将浏览器的默认样式全部去掉，更准确说就是通过重新定义标签样式。“覆盖”浏览器的CSS默认属性。最最简单的说法就是把浏览器提供的默认样式覆盖掉！这就是CSS reset。

**重置原因**

因为浏览器的品种很多，每个浏览器的默认样式也是不同的，比如<button>标签，在IE浏览器、Firefox浏览器以及Safari浏览器中的样式都是不同的，所以，通过重置button标签的CSS属性，然后再将它统一定义，就可以产生相同的显示效果。

# 浏览器及前缀

## 主流浏览器

| 浏览器名称  |     内核     |
| :---------: | :----------: |
| 谷歌google  |    webkit    |
| 火狐firefox |    gecko     |
|   safari    |    webkit    |
|  欧朋opera  | blink presto |
|     IE      |   trident    |

## 浏览器前缀

​	使用一些css3的属性的时候应该考虑到不同浏览器的内核兼容情况，需要针对不同的内核使用不同的浏览器前缀。

| 浏览器名称 |   前缀   |
| :--------: | :------: |
|   google   | -webkit- |
|   safari   | -webkit- |
|     ie     |   -ms-   |
|  firefox   |  -moz-   |
|   opera    |   -o-    |

注：浏览器前缀自动补全的网址:http://autoprefixer.github.io

# css3

## 概念

​	CSS3是css技术的升级版本，CSS3语言开发是朝着模块化发展的。以前的规范作为一个模块实在是太庞大而且比较复杂，所以，把它分解为一些小的模块，更多新的模块也被加入进来。这些模块包括： 盒子模型、列表模块、超链接方式 、语言模块 、背景和边框 、文字特效 、多栏布局等。 

## 优点 

​	CSS3将完全向后兼容，所以没有必要修改现在的设计来让它们继续运作。网络浏览器也还将继续支持CSS2。对我们来说，CSS3主要的影响是将可以使用新的可用的选择器和属性，这些会允许实现新的设计效果（譬如动态和渐变），而且可以很简单的设计出现在的设计效果（比如说使用分栏） 

## 渐进增强和优雅降级

#### 渐进增强 progressive enhancement

​	针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。  

#### 优雅降级 graceful degradation

​	一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。  

#### 区别

​	优雅降级是从复杂的现状开始，并试图减少用户体验的供给，而渐进增强则是从一个非常基础的，能够起作用的版本开始，并不断扩充，以适应未来环境的需要。降级（功能衰减）意味着往回看；而渐进增强则意味着朝前看，同时保证其根基处于安全地带。 

## CSS3选择器

### 1.层级选择器

**E>F 子选择器** 

​	选择匹配的F元素，且匹配的F元素是所匹配的E元素的子元素

**E+F 相邻兄弟选择器** 

​	选择匹配的F元素，且匹配的F元素紧位于匹配的E元素的后面

**E~F 通用选择器** 

​	选择匹配的F元素，且位于匹配的E元素后的所有匹配的F元素

### 2.属性选择器

注：E（elements元素）、attr（属性）、value（值）

E[attr]				只使用属性名，但没有确定任何属性值 
E[attr=value]			指定属性名，并指定了该属性的属性值 
E[attr**^**=value]		指定了属性名，并且有属性值，属性值是以value**开头**的 
E[attr**$**=value]		指定了属性名，并且有属性值，而且属性值是以value**结束**的 
E[attr*=value]		指定了属性名，并且有属性值，而且属值中**包含**了value 
E[attr~=value]		指定属性名，并且具有属性值，此属性值是一个词列表，并且以空格隔开，其中词列表中包含了一个 valu词，而且等号前面的“〜”不能不写 

E[attr|=value]		指定了属性名，并且属性值是value或者以“value-”开头的值（比如说zh-cn ）

### 3.伪类选择器

####  （1）结构性伪类选择器


:nth-child(x) 选择第x个元素
:nth-child(n) 全选
:nth-child(2n) 选择偶数
:nth-child(2n+1) 奇数

:first-child 第一个	IE7就可以支持
:last-child 最后一个

:only-child 唯一的一个子元素，这个伪类一般用的比较少，比如上述代码匹配的是div下的有且仅有一个的p，也就是说，如果div内有多个p，将不匹配。

Tip:  当我们使用:nth-of-type的时候，前面一定要加上元素名不然太猛了

E:first-of-type 选择同种类型下的第一个元素
E:last-of-type 选择同种类型下最后一个元素
E:only-of-type 选择同种类型下唯一的元素


**nth-child(x) 选择第x个元素**

**X:nth-of-type(n)匹配同类型中的第n个同级兄弟元素X**

X:only-of-type  同类型中唯一兄弟元素的X
X:first-of-type 同级兄弟元素中的第一个X元素
X:nth-last-child(n)从最后一个开始算索引。
X:nth-last-of-type(n) 匹配同类型中的倒数第n个同级兄弟元素X

**X:root匹配文档的根元素**。在HTML（标准通用标记语言下的一个应用）中，根元素永远是HTML
**X:empty匹配没有任何子元素（包括包含文本）的元素X**

#### （2）目标伪类选择器

E:target	选取目标元素

#### （3）UI 元素状态伪类选择器

E:enabled  选择可用状态下的标签    常用于input
**E:disabled**  选择不可用状态下的标签    常用于input
E:checked 选择所有用户界面（form表单）中处于选中状态的元素E
E:selection 选择E元素中被用户选中或处于高亮状态的部分    ::selection只能设置背景颜色和文本颜色

:read-write 可读可写 正常状态的input就可以被选中
:read-only 可读，只有在input的状态为readonly时才会被选中

伪类与伪元素的区别：

伪类：当标签进行CSS样式操作时，使用伪类操作的样式相当于作用到元素的本身；

伪元素：当标签进行CSS样式操作时，使用伪类操作的样式相当于作用到一个虚拟的标签的身上

#### （4）否定伪类选择器

E:not(s)	（IE6-8浏览器不支持:not()选择器。）
匹配所有不匹配简单选择符s的元素E

#### （5）动态伪类选择器

E:link
	  选择匹配的E元素，而且匹配元素被定义了超链接并未被访问过。常用于链接描点上 
E:visited 
	选择匹配的E元素，而且匹配元素被定义了超链接并已被访问过。常用于链接描点上 
E:active
	选择匹配的E元素，且匹配元素被激活。常用于链接描点和按钮上 
E:hover
	选择匹配的E元素，且用户鼠标停留在元素E上。IE6及以下浏览器仅支持a:hover 
E:focus

​	 用户行为选择器 选择匹配的E元素，而且匹配元素获取焦点

## 文本属性

#### 1.text-shadow   文字阴影

参数:
		x  	x轴的偏移量
		y 	y轴的偏移量
		blur 模糊值  带有单位  值越大越模糊，负值消失
		color 颜色
多阴影：写完一组值之后，用逗号分隔继续写下一组......

#### 2.text-stroke ： 文字描边

参数:
		w 描边的宽度
		color 颜色
Tip:谷歌浏览器需要使用浏览器前缀 ，目前只有谷歌支持(待测试)

#### 3.text-overflow   文字溢出隐藏

#### 4.direction    文字排列方式

#### 5.word-break 自动换行的处理方式

参数：
		normal 
		break-all 允许在单词内换行
		keep-all 只允许在空格或者连字符处换行

#### 6.word-wrap  

标明是否允许浏览器在单词内进行断句，这是为了防止当一个字符串太长而找不到它的自然断句点时产生溢出现象。

​	参数：
		normal 
		break-word  在长单词或url地址内部进行换行

#### 7.字体图标@font-face

~~~css
@font-face的语法规则：@font-face {
font-family: <YourWebFontName>; 
src: <source> <format>]*; 
[font-weight: <weight>]; 
[font-style: <style>]; 
}
~~~

#### @font-face语法说明：

使用原因：能够自由的按照文字的方式对图标进行适当的更改

引入字体图标首先
	需要下载字体图标库
	下载完成之后引入对应的css文件
	在给需要的标签设置字体图标对应的类名
全套字体图标：
	http://www.bootcss.com/p/font-awesome/
定制字体图标：
	https://icomoon.io/app/#/select

1、YourWebFontName:此值指的就是你自定义的字体名称，最好是使用你下载的默认字体，他将被引用到你的Web元素中的font-family。如“font-family:"YourWebFontName";” 
2、source:此值指的是你自定义的字体的存放路径，可以是相对路径也可以是绝路径； 
3、format：此值指的是你自定义的字体的格式，主要用来帮助浏览器识别，其值主要有以下几种类型：truetype,opentype,truetype-aat,embedded-opentype,avg等； 
4、weight和style:这两个值大家一定很熟悉，weight定义字体是否为粗体，style主要定义字体样式，如斜体。

实例：

~~~css 
@font-face {
font-family: 'icomoon';
src:url('fonts/icomoon.eot');
src:url('fonts/icomoon.eot?#iefix') format('embedded-opentype'),
url('fonts/icomoon.svg#icomoon') format('svg'),
url('fonts/icomoon.woff') format('woff'),
url('fonts/icomoon.ttf') format('truetype');
font-weight: normal;
font-style: normal;
}
~~~

#### 8.雪碧图/css精灵图

使用原因：

减少客户端向服务端发送的http请求的次数，减少服务端的压力

#### 9.background-size

 参数：
		length   带有单位的数值
		percentage   百分比
		cover   覆盖整个盒子 等比放大
		contain  把整个图片完整的包裹进盒子当中 等比放大

background-size：100px;
**当这个属性设置一个值的时候，这个值表示宽度，高度为自适应。**
	**Tip：当设置一个值的时候，不要错误的把高度也想象成这个值。**
如果设置两个值的时候，第一个值表示宽度，第二个值表示高度。

当值设置为百分比的时候，是以父容器的宽度和高度为参考。
**cover 表示不去考虑图片能不能够完整的显示，而是要把容器占满。**
**contain 表示不去考虑图片是否占满盒子，而是考虑图片显示完整。**

300 400
宽高比3:4

Tip:ie6-8不能够支持

插件:backgroundsize.min.htc

#### 10.background-origin  背景位置

​	相关属性:
		padding-box   图片会占满padding+内容
		border-box    图片会占满border+padding+内容
		content-box  图片会占满内容区域

####11.background-clip 背景裁切 

​	相关属性:
		padding-box
		border-box   默认值
		content-box

#### 12.多背景

​	**多背景，顺序靠前，层级就高**（逗号分隔）
	background: url(./images/xx1.jpg) no-repeat left top,
				url(./images/xx3.jpg) no-repeat left bottom,
				url(./images/xx4.jpg) no-repeat right top,
				url(./images/xx5.jpg) no-repeat right bottom,
				url(./images/xx2.gif) no-repeat center center;

# 颜色和渐变

1.HSL：通过对色相(H)、饱和度(S)、明度(L)三个颜色通道的变化以及它们相互之间的叠加来得到各式各样的颜色。

H：Hue(色调)。0(或360)表示红色，120表示绿色，240表示蓝色，也可取其他数值来指定颜色。取值为：0 - 360
S：Saturation(饱和度)。取值为：0.0% - 100.0%
L：Lightness(亮度)。取值为：0.0% - 100.0%

2.HSLA：此色彩模式与HSL相同，只是在HSL模式上新增了Alpha透明度
	取值：
		H：Hue(色调)。0(或360)表示红色，120表示绿色，240表示蓝色，也可取其他数值
			来指定颜色。取值为：0 - 360
		S：Saturation(饱和度)。取值为：0.0% - 100.0%
		L：Lightness(亮度)。取值为：0.0% - 100.0%
		A：Alpha透明度。取值0~1之间。

3.rbg、英文单词 、进制 rgba。

不透明度:
	rgba：不会被继承，所以内容不会透明
	opacity: 因为会被继承，所以使用的时候会连字都变得透明

4.颜色渐变 --- 应用在元素的背景上，渐变分为两种：线性渐变 和 径向渐变

### 线性渐变linear-gradient()



1.线性渐变的初始颜色变化默认是从上到下。而且，渐变必须设置在background（images）的身上。

​	background-image: linear-gradient(blue,red);

2.线性渐变是支持多个颜色渐变的。

​	background: linear-gradient(red,yellow,blue,pink);

3.设置渐变方向

​	background: -webkit-linear-gradient(bottom,red,pink);

如果在参数里直接设置方向，那么需要加浏览器前缀,  如果在方向的前面加上**to**，那么就**不需要加浏览器前缀**。

ackground: linear-gradient(to left,red,pink);

​	to left 、 to right 、 to top 、to bottom ,**没有to center,**

4.当然，关于方向我们也可以组合来使用：to left top 或者top left bottom.....

5.我们除了设置具体的方向值，还可以通过  angle 来设置角度。在代码中deg表示角度

​	0deg表示从下向上，如果角度为正，则为顺时针，如果角度为负，则为逆时针。

6.渐变百分比
	background: linear-gradient(to left,red 10%,black 90%);
	方向：从右到左，表示从起始方向开始，从右向左的10%为纯红色，从10%到90%为红色向黑色的渐变色，剩下的为纯黑色。

7.线性渐变在IE:
	filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ffffff',
	endColorstr='#ff0000',GradientType='1');   
GradientType = 0 方向是从上向下  1为从左向右

8.重复线性渐变
	一个渐变的过程已经完成，后续重复的进行这个过程。
	repeating-linear-gradient() ;

### radial-gradient:径向渐变

方向：
	eft top right bottom ，前面要加webkit，也可以设置具体的值：apx  bpx 

还可以设置圆的形状：正圆:circle 	椭圆:ellipse

# 圆角border-radius

​	boder-top-left-radius: 左上
	border-top-right-radius:右上
	border-bottom-right-radius:右下
	border-bottom-left-riadus:左下	

border-radius：可以设置一个值到四个值。
	顺序：
		1个值：四个角
		2个值: 左上右下 	右上左下
		三个值:  左上	  	右上左下  	右下 	
		四个值: 左上		 右上	  右下	  左下 	

如何通过border-radius做一个圆

border-radius=50%（盒子宽高一样），其中的50%是以盒子的宽高为参考的

# border-image 边框图片

​	目前IE11以上才支持	

border-image 是一个简写值，分别有以下属性值,

​	**border-image-source	图片地址**

​	**border-image-slice   图片切片**

值：number  | 百分比  {1,4}
	Tip：{1,4} 表示最少一个值，最多四个值指定边框图像顶部，右侧，底部，左侧内偏移量。没有具体的单位值，px em rem都不可以。只可以用数字或者百分比。

​		**border-image-width  图片宽度**

值：lenghth | number | 百分比 {1,4}

​		**border-image-outset  图片外凸**
		**border-image-repeat  图片重复**

值：round平铺占满，位置不够把原来放大一部分，但不会放半个。

​	repeat平铺占满，位置不够放半个

​	stretch不平铺，拉伸或缩小图片 

# 盒子阴影box-shadow

属性值：	h-shadow：水平阴影的位置 允许负值
		v-shadow：垂直阴影的位置 允许负值
		blur : 模糊值
		spread 阴影的大小		允许负值
		color	颜色
		inset 	将盒子阴影从外面放到盒子里面

也可以设置多阴影，之间用逗号分隔。



# 弹性盒子模型

怪异盒子模型（IE盒子模型）：
	在ie6以下，在非标准模式下的渲染下，设置的宽度和高度就是元素在网页中实际占据的宽度和高度。
	开启怪异盒子模型：
		box-sizing:border-box|content-box	

标准盒子模型（W3C盒子模型）：

​	在标准模式下，一个盒子的宽度和高度是元素的宽高加上左右padding、左右border和左右margin

弹性盒子模型核心概念：
	主轴
	侧轴
	弹性容器
	弹性子元素	

### **display:flex；**

​	将元素变为弹性容器，那么这个元素里面的子元素自然而然的就变成了弹性子元素。(容器是一个块级元素)

### **display:inline-flex**;

​	容器是一个行内flex元素。

### 弹性容器(父元素)专用属性

#### 1.flex-direction:

​	作用：弹性容器中子元素的排列方式(**主轴排列方式**)【子元素在主轴上的排列方式】
	属性：
		row:默认在一行排列
		row-reverse:反转横向排列（右对齐，从后往前排，最后一项排在最前面。）
		column：纵向排列。
		column-reverse：反转纵向排列，从下往上排，最后一项排在最上面

#### 2.flex-wrap:

​	作用:设置弹性盒子的子元素超出父容器时是否换行 
	属性值：
		nowrap: 默认值。规定元素不拆行或不拆列。
		wrap:规定元素在必要的时候拆行或拆列。
		wrap-reverse:规定元素在必要的时候拆行或拆列，但是以相反的顺序。
	

#### 3.flex-flow: flex-direction和flex-wrap的缩写

#### 4.align-item:

​	作用:设置弹性盒子元素在**侧轴（纵轴）**方向上的对齐方式
	属性值：
		flex-start：弹性盒子元素的侧轴（纵轴）起始位置的边界紧靠住该行的侧轴**起始**边界。
        	flex-end：弹性盒子元素的侧轴（纵轴）起始位置的边界紧靠住该行的侧轴**结束**边界。
       		 center：弹性盒子元素在该行的侧轴（纵轴）上居中放置。（如果该行的尺寸小于弹性盒子元素的尺寸，则会向两个方向溢出相同的长度）。
       		 baseline：如弹性盒子元素的行内轴与侧轴为同一条，则该值与'flex-start'等效。其它情况下，该值将参与基线对齐。

#### 5.align-content（侧轴多行排列）

​	作用:修改 flex-wrap 属性的行为，类似 align-items, 但不是设置子元素对齐，而是设置行对齐(行与行的对其方式)
	属性:
		flex-start：没有行间距
		flex-end：底对齐没有行间距
		center：居中没有行间距
		space-between：两端对齐，中间自动分配
		space-around：自动分配距离

**说明**
  	当伸缩容器的侧轴还有多余空间时，本属性可以用来调准「伸缩行」在伸缩容器里的对齐方式，
  	这与调准伸缩项目在主轴上对齐方式的 <' justify-content'> 属性类似。
  	请注意本属性在只有一行的伸缩容器上没有效果。

####6.justify-content（横轴多个排列）

​	作用:设置弹性盒子元素在主轴（横轴）方向上的对齐方式，内容对齐属性应用在弹性容器上，把弹性项沿着弹性容器的主轴线（main axis）对齐
	属性：
		flex-start：默认，顶端对齐
        	flex-end：末端对齐
        	center：居中对齐
        	space-between：两端对齐，中间自动分配
        	space-around：自动分配距离

## 弹性子元素的相关属性

#### 1.order（默认值0）

设置弹性盒子的子元素排列顺序。 number排序优先级，数字越大越往后排，默认为0，支持负数。

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>order</title>
    <style>
        body {
            display: flex;
        }
        div:nth-of-type(1) {
            width: 100px;
            height: 100px;
            background-color: lightblue;
            order:4;
        }
        div:nth-of-type(2) {
            width: 100px;
            height: 100px;
            background-color: lightcoral;
            order:3;
        }
        div:nth-of-type(3) {
            width: 100px;
            height: 100px;
            background-color: lightsalmon;
            order:2;
        }
        div:nth-of-type(4) {
            width: 100px;
            height: 100px;
            background-color: coral;
            order:1;
        }
    </style>
</head>
<body>
<div>1</div>
<div>2</div>
<div>3</div>
<div>4</div>
</body>
</html>
~~~

#### 2.flex-grow（默认值0）

设置或检索弹性盒子元素的扩展比率。

~~~html
参数：<integer>：一个数字，规定项目将相对于其他灵活的项目进行扩展的量。
~~~

瓜分容器的剩余空间。
	什么是剩余空间？
		假设父元素的宽度是500px，有三个子元素，每个宽度是100，那么剩余空间就是500 - 100 * 3 = 200。而flex-grow就是用来瓜分剩余空间的。例如第一个盒子属性为flex-grow:1;那么剩余空间就会被分成一份，第一个盒子额外的占据了这一份。如果这个时候第二个盒子flex-grow:2;那么此时剩余空间就被分成三分，第一个盒子占一份，第二个盒子占两份。

~~~html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>flex-grow</title>
    <style>
        /*剩余空间:600px - 100*3 = 300px*/
        nav {
            height: 500px;
            width: 600px;
            background-color: lightblue;
            display:flex;
        }
        nav div {
            width: 100px;
            height: 100px;
            background-color: lightsalmon;
        }
        div:nth-of-type(1){
            flex-grow:1;
        }
        div:nth-of-type(2){
            flex-grow:2;
        }
        div:nth-of-type(3){
            flex-grow:1;
        }
    </style>
</head>
<body>
    <nav>
        <div>1</div>
        <div>2</div>
        <div>3</div>
    </nav>
</body>
</html>
~~~

####3.flex-basis（默认值auto）

用于设置或检索弹性盒伸缩基准值。

~~~html
参数：<integer>：一个长度单位或者一个百分比，规定元素的初始长度。auto：默认值。长度等于元素的长度。如果该项目未指定长度，则长度将根据内容决定。
~~~

**flex-basis是width的替代品**。如果子元素设置了flex-basis或者width，那么在分配空间之前，就会跟父容器预约这么多
的空间，然后剩下的才归到剩余空间，然后父容器再把剩余空间分配给flex-grow的容器。如果同时设置了flex-basis
和width，那么width的属性就会被覆盖，也就是说flex-basis的优先级比width高。

#### 4.flex-shrink（默认值1）

指定了 flex 元素的收缩规则。flex 元素仅在默认宽度之和大于容器的时候才会发生收缩，其收缩的大小是依据 flex-shrink 的值。

```html
参数：<integer>：一个数字，规定项目将相对于其他灵活的项目进行收缩的量。默认值是 1。
```


​	 当父容器的剩余空间为0的时候，并且默认处于非换行状态的情况下，子元素是没有办法利用弹性容器的剩余空间
进行扩展的。
	如果如容器的剩余宽度为负数的情况下(子元素的宽度之和大于父容器的宽度)，那么子元素就会被收缩。收缩的比例为1:1
	例如，一个弹性容器中有三个子元素，那么他们的收缩比例就为1:1:1.如果这个时候，第一个子元素设置了flex-shrink:2;那么我们就会发现，这个元素比其他两个元素收缩的幅度更大。同时呢，因为第一个子元素空间的更多收缩，所以第二个和第三个元素就会获得更多的空间。我们假设第二个和第三个盒子收缩比例为x1,那么第一个盒子的收缩比例就为x2.

例：

父元素 500px。三个子元素分别设置为 150px，200px，300px。三个子元素的 flex-shrink 的值分别为 1，2，3。首先，计算子元素溢出多少：150 + 200 + 300 - 500 = -150px。那这 -150px 将由三个元素的分别收缩一定的量来弥补。具体的计算方式为：每个元素收缩的权重为其 flex-shrink 乘以其宽度。

所以总权重为 1 * 150 + 2 * 200 + 3 * 300 = 1450   总权重: 收缩比 * 宽度 之和

三个元素分别收缩：
	溢出值 * 收缩比  * width / 总权重 = 收缩的宽度
	150 * 1(flex-shrink) * 150(width) / 1450 = -15.5
	150 * 2(flex-shrink) * 200(width) / 1450 = -41.4
	150 * 3(flex-shrink) * 300(width) / 1450 = -93.1
三个元素的最终宽度分别为：

​	150 - 15.5 = 134.5
	200 - 41.4 = 158.6
	300 - 93.1 = 206.9
同样，当所有元素的 flex-shrink 之和小于 1 时，计算方式也会有所不同：此时，并不会收缩所有的空间，而只会收缩 flex-shrink 之和相对于 1 的比例的空间。还是上面的例子，但是 flex-shrink 分别改为 0.1，0.2，0.3。

于是总权重为 145（正好缩小 10 倍，略去计算公式）。

三个元素收缩总和并不是 150px，而是只会收缩 150px 的 (0.1 + 0.2 + 0.3) / 1 即 60% 的空间：90px。

每个元素收缩的空间为：

​	90 * 0.1(flex-shrink) * 150(width) / 145 = 9.31
	90 * 0.2(flex-shrink) * 200(width) / 145 = 24.83
	90 * 0.3(flex-shrink) * 300(width) / 145 = 55.86
三个元素的最终宽度分别为：

​	150 - 9.31 = 140.69
	200 - 24.83 = 175.17
	300 - 55.86 = 244.14

#### 5.align-self在弹性子元素上使用。

覆盖容器的 align-items 属性，值与容器属性一样，只是这个是单独的设置某个元素。


## flex缩写（默认值0,1，auto）

​	flex是flex-grow,flex-shrink和flex-basis的缩写，flex属性用于设置或检索弹性盒模型对象的子元素如何分配空间，flex属性值可以只指定一个属性的值，而另外的属性值采用各自在flex属性中的的初始值，但是有一点要注意的是：flex属性中flex-grow和flex-basis的初始值和它们原始的默认值不同，至于为什么不同，mdn中有明确的说过这样的设计是为了让「flex」缩写在最常见的情景下比较好用。

##### **flex中对应各属性的初始值（1,1,0）

flex-grow
  flex-grow用于设置各item项按对应比例划分剩余空间，若flex中没有指定flex-grow,则相当于设置了flex-grow:1

flex-shrink
  flex-shrink用于设置item的总和超出容器空间时，各item的收缩比例，若flex中没有指定flex-shrink,则等同于设置了flex-shrink:1

flex-basis   
  flex-basis用于设置各item项的伸缩基准值，可以取值为长度或百分比，如果flex中省略了该属性，则相当于设置了flex-basis:0.

flex的不同取值

~~~html
	flex的值的完整写法是[<flex-grow> <flex-shrink> <flex-basis>],不过它的取值还有可能是单个数字或者单个百分比等，不同种类的取值所表示的意思是大有不同的。
~~~

**flex值为none**
  当flex为none时,等同于flex: 0 0 auto;	

**flex值为auto**
  当flex为auto时，等同于flex: 1 1 auto;

**flex值为一个非负数字**
  当flex取值为一个数字，则该数字是设置的flex-grow值，其它两个属性用初始值，如flex:1时，等同于flex: 1 1 0%

**flex值为两个非负数字**
  当flex取值为2个数字时，相当于设置的flex-grow和flex-shrink值，flex-basis取值为初始值， 如flex:1 0时，等同于flex: 1 0 0%

**flex值为一个数字和一个长度或百分比时**
  当flex取值为1个数字和1个长度或百分比时，设置的是flex-grow和flex-basis的值，flex-shrink值为初始值，如flex:1 20%,等同于flex: 1 1 20%

# 响应式

相关人物介绍：
	伊桑·马科特（Ethan Marcotte）在2010年首先提出了响应式网页设计（RWD,Responsive Web Design）这个术语。在他的一篇文章《Responsive Web Design · An A List Apart Article》中他将已有的三种发开技巧（弹性图片，弹性网格布局，媒体与媒体查询） 进行了整合，命名为响应式网页设计。那什么才是真正的响应式设计？马科特说，真正的响应式设计方法不仅仅是根据可视区域大小而改变网页布局，而是要从整体上颠覆当前网页的设计方法，是针对任意设备的网页内容进行完美布局的一种显示机制。(就是一个网站能够兼容多个终端——而不是为每个终端做一个特定的版本。这个概念是为解决移动互联网浏览而诞生的。 )

## 当今流行的网页布局方案

#### 固定布局

​	以像素作为页面的基本单位，不管设备屏幕及浏览器宽度，只设计一套尺寸。

#### 可切换的固定布局

​	同样以像素作为页面单位，参考主流设备尺寸，设计几套不同宽度的布局。通过识别的屏幕尺寸或 浏览器宽度，选择最合适的那套宽度布局。

#### 响应式布局（ Responsive layout ）

​	对页面进行响应式的设计实现，需要对相同内容进行不同宽度的布局设计，有两种方式：pc优先（从pc端开始向下设计）；移动优先（从移动端向上设计）；无论基于那种模式的设计，要兼容所有设备，布局响应时不可避免地需要对模块布局做一些变化（发生布局改变的临界点称之为断点）。

#### 弹性布局

​	以百分比作为页面的基本单位，可以适应一定范围内所有尺寸的设备屏幕及浏览器宽度，并能完美利用有效空间展现最佳效果。

#### 混合布局

​	同弹性布局类似，可以适应一定范围内所有尺寸的设备屏幕及浏览器宽度，并能完美利用有效空间展现最佳效果；只是混合像素和百分比两种单位作为页面单位。

## 响应式布局的优缺点

**设计特点**
    面对不同分辨率设备灵活性强
    能够快捷解决多设备显示适应问题
**缺点：**
    兼容各种设备工作量大，效率低下
    代码累赘，会出现隐藏无用的元素，加载时间加长                                                                                                                 	     	                其实这是一种折中性质的设计解决方案，多方面因素影响而达不到最佳效果，一定程度上改变了网站原有的布局结构，会出现用户混淆的情况。

### 开发响应式网页的前期准备

#### 1.Meta标签的设置

~~~html
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0,minimum-scale=1.0, user-scalable=no">
~~~

​    这段代码的几个参数解释：
    width = device-width：宽度等于当前设备的宽度
    initial-scale： 初始的缩放比例（默认设置为1.0）
    minimum-scale：允许用户缩放到的最小比例（默认设置为1.0）
    maximum-scale：允许用户缩放到的最大比例（默认设置为1.0）
    user-scalable：用户是否可以手动缩放（默认设置为no，因为我们不希望用户放大缩小页面）

#### meta标签其他可选设置

H5页面窗口自动调整到设备宽度，并禁止用户缩放页面

~~~~html
<meta name="viewport" content="width=device-width,initial-scale=1.0,minimum-scale=1.0,maximum-scale=1.0,user-scalable=no" >
~~~~

~~~~html
忽略将页面中的数字识别为电话号码
<meta name="format-detection" content="telephone=no" >

忽略Android平台中对邮箱地址的识别
<meta name="format-detection" content="email=no" >

当网站添加到主屏幕快速启动方式，可隐藏地址栏，仅针对ios的safari
<meta name="apple-mobile-web-app-capable" content="yes" >
<!-- ios7.0版本以后，safari上已看不到效果 -->

将网站添加到主屏幕快速启动方式，仅针对ios的safari顶端状态条的样式
<meta name="apple-mobile-web-app-status-bar-style" content="black" />
~~~~

####3. rem 和 vw/vh

rem是以html根元素的字体大小为参考。默认情况下，1rem = 16px，此时html相当于font-size:100%。

html {
    font-size:100px;
   }

 1rem =16px ;


vh|vw这两个单位，以视口为参考。
视口单位中的“视口”，桌面端指的是浏览器的可视区域；移动端指的就是Viewport中的Layout Viewport。

**1vw等于视口宽度的1%。**
**1vh等于视口高度的1%。**
**注：并且会随着视口的变化而变化**。

#### 4 断点

断点，响应式网页发生变化的临界点。

#### 5媒体查询(Media Query) 

​	媒体查询是css当中的一种技术，通过这种技术可以判断用户的浏览器宽度，类型，以及横屏还是竖屏等。

响应式网页的实现方式有很多，主流方式是通过媒体查询的形式来实现响应式网页。

#### 6.媒体查询特性

​	媒体查询可以让我们根据设备显示器的特性（如视口宽度、屏幕比例、设备方向：横向或纵向）为其设定CSS样式，
媒体查询由媒体类型和一个或多个检测媒体特性的条件表达式组成。**媒体查询中可用于检测的媒体特性有 width 、**
**height 和 color （等**）。使用媒体查询，可以在不改变页面内容的情况下，为特定的一些输出设备定制显示效果。

#### 7. 媒体查询基本语法

@media 媒体类型  关键字 (条件1) 关键字 (条件2) ... {
    css code
}

常用媒体类型：
    **all     所有设备**
    aural    听觉设备
    braille   点字触碰设备
    **print    打印**
    tty      打字机设备
    tv      电视机等设备
    **screen  显示器、笔记本、电脑等设备**
    ...

上述的设备有很多，只是简单的陈述几种，但是我们常用的设备只有all和screen

**关键字：**
    and 并且 和
    not 否定、排除
    only 限定
    or 或者
**条件：**
    min-width:400px

媒体查询语法示例:
    @media all (min-width:480px) {
        html {
            background:red;
        }
    }

上述示例表示当用户设备屏幕处于最小宽度为480px以上的时候，网页的背景颜色为红色

~~~~css
/* 竖屏 */
@media screen and (orientation:portrait) {对应样式}

/* 横屏 */
@media screen and (orientation:landscape){对应样式}
~~~~

#### 8. 常用断点值

​	320px
	480px
	768px
	1024px

#### 9. css2中媒体查询的用法

​	其实并不是只有CSS3才支持Media的用法，早在CSS2开始就已经支持Media，具体用法，就是在HTML页面的head标签中插入如下的一段代码

~~~css
<link rel="stylesheet" type="text/css" media="screen" href="style.css">;
想知道现在的移动设备是不是纵向放置的显示屏，可以这样写：
<link rel=“stylesheet” type=“text/css” media=“screen and  (orientation:portrait)”  	href="style.css">
orientation:portrait：指定输出设备中的页面可见区域高度大于或等于宽度
landscape：除portrait值情况外，都是landscape
第一段的代码也用CSS2来实现，让它一样可以让页面宽度小于960的执行指定的样式文件：
<link rel="stylesheet" type="text/css" media="screen and (max-width:960px)" href="style.css">
~~~

#### 10.移动端优先和pc端优先

​	在开发响应式网页的时候，我们有两种选择，一种是从移动端开始开发然后逐渐升级到pc，这种方式叫做移动端优先
pc端优先则正好相反。

# 移动端相关布局知识点

通过弹性盒子模型+rem进行移动端项目开发

### 像素

​	像素，又称画素，是图像显示的基本单位，译自英文“pixel”，pix是英语单词picture的常用简写，加上英语单词“元素”element，就得到pixel，故“像素”表示“图像元素”之意，有时亦被称为pel(picture element)

　　像素是网页布局的基础。一个像素就是计算机能够显示一种特定颜色的最小区域。当设备尺寸相同但像素变得更密集时，屏幕能显示的画面的过渡更细致，网站看起来更明快。 

ppi是**指屏幕上每英寸可以显示的像素点的数量**，即**屏幕像素密度**。同一屏幕大小，ppi越多，越清晰。

### 分类

实际上像素分为两种：设备像素和CSS像素

　　1、设备像素(device independent pixels): 设备屏幕的物理像素，任何设备的物理像素的数量都是固定的

​	2、CSS像素(CSS pixels): 又称为逻辑像素，是为web开发者创造的，在CSS和javascript中使用的一个抽象的层（实际不存在的，比如手机上的世界地图） 

### 缩放

在桌面端，css的1个像素往往都是对应着电脑屏幕的1个物理像素。

一个CSS像素完全覆盖了一个设备像素，而在手机端，由于屏幕尺寸的限制，缩放是经常性的操作。

​	不论我们进行缩小或放大操作，元素设置的CSS像素(如width:300px)是始终不变的，而一个CSS像素对应多少个设备像素是根据当前的缩放比例来决定的。

### DPR

设备像素比DPR(devicePixelRatio)是默认缩放为100%的情况下，设备像素和CSS像素的比值

**DPR =** **设备像素 / CSS****像素(****某一方向上)**

 	在早先的移动设备中，并没有DPR的概念。随着技术的发展，移动设备的屏幕像素密度越来越高。从iphone4开始，苹果公司推出了所谓的retina视网膜屏幕。之所以叫做视网膜屏幕，是因为屏幕的PPI(屏幕像素密度)太高，人的视网膜无法分辨出屏幕上的像素点。iphone4的分辨率提高了一倍，但屏幕尺寸却没有变化，这意味着同样大小的屏幕上，像素多了一倍，于是**DPR = 2**

以iphone5为例，iphone5的CSS像素为320px*568px，DPR是2，所以其设备像素为640px1136px

### 设计图和DPR

​	在进行项目开发的时候，我们需要额外的注意，如果设计图宽度为640px，那么我们需要考虑的dpr为2.

如果设计图宽度为1080px的时候，我们考虑的DPR就为3。

# 多列布局

## 属性

### 1.column-count规定元素应该被分隔的列数

适用于：除table外的非替换块级元素, table-cells, inline-block元素

值：number列的最佳数目

​	auto列数自动，将取决于其他因素，如column-width

### 2.column-fill指定如何填充列

所有浏览器都不支持

值：balance所有列的高度与其中最高的一列统一

​	auto列高度自适应内容

### 3.column-gap指定列与列之间的间隙

值：length用长度值来定义列与列之间的间隙。不允许负值 

​	normal与 <' font-size '> 大小相同。假设该对象的font-size为16px，则normal值为16px，类推。 

### 4.column-rule所有column-rule-*的属性的简写

​	column-rule: column-rule-width column-rule-style column-rule-color

#### 	4.1column-rule-color指定两列间边框的颜色

​		值：column-rule-color:color

#### 	4.2column-rule-style指定两列间边框的样式

​		值：column-rule-style: none|hidden|dotted|dashed|solid|double|groove|ridge|inset|outset;

#### 	4.3column-rule-width指定两列间边框的宽度

​		值：column-rule-width: thin|medium|thick|length;

###5.column-span指定元素要跨的列数

​	值：1或者none,横跨一列

​		all横跨所有列

### 6.column-width指定列的宽度

​	值：auto浏览器将决定列的宽度

​		length指定列宽的长度，column-count会产生影响













































































































































































































 
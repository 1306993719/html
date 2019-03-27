# HTML 基础语法

## 什么是网页？什么是html?

我们在日常的学习工作当中，避免不了使用电脑的浏览器或者手机的浏览器查一些资料。我们通过浏览器访问的是一个又一个的网站，而这些网站给我们展示信息的页面，我们就称之为网页。

而一个网站就是由很多的网页组成，而网页又是通过html编写的。



> 概念:
>
> (Hyper Text Markup Language)超文本标记语言，是用来描述网页的一种语言
>
>     1. 超文本(Hyper Text):不只包括文本，也可以包括图片、链接、音乐、视频等非文本元素
>     2. 标记语言(Markup Language):标记语言是一套标记标签，HTML使用标记标签来描述网页



## 什么是标签

一组尖括号，里面包裹着关键词，就组成了标签。

例如: `<html>`。

html的标签当中分为单标签和双标签。

单标签: `<img>`、`<input>`、`<br>`等。

双标签:HTML标签通常是成对出现的，比如 <b> 和 </b>。第一个标签是开始标签，第二个标签是结束标签；开始标签和结束标签也被称为开放标签和闭合标签

> 注意：HTML标签对大小写不敏感，但要全小写

## 属性

在每一个标签当中，都可以设置一些属性。属性能够展示和提供更多的html信息。

属性以名值对(名称/值)的形式出现，且总是在HTML元素的开始标签中规定。

例如在标签当中经常出现下面的一些属性:

| 属性名 |    属性作用    |
| :----: | :------------: |
| class  |    元素类名    |
|   id   |     元素id     |
| style  | 元素的行内样式 |

## 元素

从开始标签到结束标签的所有代码

HTML元素以开始标签起始，以结束标签终止，元素的内容是开始标签与结束标签之间的内容。



## 文档

html网页文件也可以叫做html文档或者网页文档，由嵌套的html元素组成。

注意：浏览器不会显示HTML标签，而是使用标签来解释页面的内容



## 注释

注释是在HTML中写入的具有描述性的文本，用来解释该代码或提示其他信息。

通常情况下注释可以很好的帮助程序员了解当前代码或者相关信息。

html注释语法如下:

```html
<!--注释内容-->
```

> 注释只会出现在代码中，并不会出现在网页当中。
>
> 并且注释里面不能再次写注释，也就是注释不能嵌套。

## 实体字符

在网页当中，一些特殊的字符不能够直接输入，而是要通过实体字符来描述。

这些实体字符本质是html预留的，我们想要使用，必须使用实体字符。

| 显示结果 | 描述     | 实体名称       | 实体编号 |
| :------- | -------- | -------------- | -------- |
|          | 空格     | `&nbsp;`       | `&#160;` |
| <        | 小于号   | `&lt;`         | `&#60;`  |
| >        | 大于号   | `&gt;`         | `&#62;`    |
| &        | 和号     | `&amp;`          | `&#38;`    |
| "        | 引号     | `&quot;`         | `&#34;`    |
| '        | 撇号     | `&apos;`         | `&#39;`    |
| ￠       | 分       | `&cent;`         | `&#162;`   |
| £        | 镑       | `&pound;`        | `&#163;`   |
| ¥        | 日圆     |` &yen; `         | `&#165;`   |
| €        | 欧元     | `&euro;`         | `&#8364;`  |
| §        | 小节     | `&sect;`         | `&#167;`   |
| ©        | 版权     | `&copy;`         | `&#169;`   |
| ®        | 注册商标 | `&reg;`          | `&#174;`   |
| ™        | 商标     | `&trade;`        | `&#8482;`  |
| ×        | 乘号     | `&times;`        | `&#215;`   |
| ÷        | 除号     | `&divide;`       | `&#247;`   |

## html 中的全局属性

在html标签中可以通过属性来表达丰富的语义，而且属性也有很多的功能，下面列出了html中16个常见的html全局属性。

### html原有属性

**accesskey**

作用:浏览器用来创建激活或聚焦元素的快捷键

值：一个键盘字符例如`N`键。

支持范围:支持该属性的元素有`<a>`、`<area>`、`<button>`、`<input>`、`<label>`、`<legend>`、`<textarea>`

示例代码:

```html
<div>
        <a href="http://www.baidu.com" accesskey="b">百度</a>
        <a href="http://www.taobao.com" accesskey="t">淘宝</a>
        <a href="http://www.jd.com" accesskey="j">京东</a>
        <p>
            <b>alt</b> + <b>b</b> 打开百度
            <b>alt</b> + <b>t</b> 打开淘宝
            <b>alt</b> + <b>j</b> 打开京东
        </p>
</div>
```



> 注意：在不同的系统里面可能快捷键有些出入，例如笔者的是mac电脑，快捷键就变成了`ctrl`+`option`+键盘字符。

**class** 

作用：规定元素的一个或多个类名

值：多个类名用空格分隔

注意：类名不能以数字开头



**dir**  

作用：文字的方向

值：ltr/rtl/auto

```html
<p dir="ltr">
        hello,world
</p>
<p dir="rtl">
        hello,world
</p>
```

**id**

作用：规定元素的唯一标识

> 注意：若浏览器中出现多个id名的情况，CSS样式对所以该id名的元素都生效，但javascript脚本仅对第一个出现该id名的元素生效



**lang**
作用:规定元素内容语言。

```
en:英文
zh:中文
zh-CN：简体中文
```

zh 是中文，代表的是宏语言（Macrolanguage），zh 单独用表示中文整体，可以是方言、文言文、简繁体等混合内容。理论上 zh-CN 表示的是中国大陆中文，包含方言和简繁体，但默认指简体普通话。为了精准性，应该用独立语种替换，包括但不仅限于普通话和七大方言：

```
cmn 普通话（官话、国语）
wuu 吴语（江浙话、上海话）、czh 徽语（徽州话、严州话、吴语-徽严片）
hak 客家语
yue 粤语（广东话）
nan 闽南语（福建话、台语）、cpx 莆仙话（莆田话、兴化语）、cdo 闽东语、mnp 闽北语、zco 闽中语
gan 赣语（江西话）
hsn 湘语（湖南话）
cjy 晋语（山西话、陕北话）
```

以下所有 zh 开头写法已于 2009 年废弃，因为在语言学的分类上，中国语言学者多认为吴语、粤语、闽语等是汉语的方言，而西方学者多认为这些语言是一门和汉语同级关系的单独语种

以下两种写法均正确，后者描述更精准，但目前浏览器和操作系统都只支持前者，使用新标准可能会造成无法匹配浏览器用户定义字体、网页翻译、程序语言自动切换等功能，为了兼容性推荐使用前者

```
zh-CN 中文 (简体, 中国大陆) 对应 cmn-Hans-CN 普通话 (简体, 中国大陆)
zh-SG 中文 (简体, 新加坡)   对应 cmn-Hans-SG 普通话 (简体, 新加坡)
zh-HK 中文 (繁体, 香港)     对应 cmn-Hant-HK 普通话 (繁体, 香港)
zh-MO 中文 (繁体, 澳门)     对应 cmn-Hant-MO 普通话 (繁体, 澳门)
zh-TW 中文 (繁体, 台湾)     对应 cmn-Hant-TW 普通话 (繁体, 台湾)
```



**style**
作用:设置元素的行间样式。



**tabindex**
作用:规定元素的tab键序
值:number（1是第一个，以此类推）

```html
<div>
    <a href="https://www.baidu.com" tabindex="3">百度</a>
    <a href="https://www.taobao.com" tabindex="2">阿里</a>
    <a href="https://www.qq.com" tabindex="1">腾讯</a>   
</div>
```

**title**
作用:规定关于元素的额外信息，鼠标移到元素上时显示一段提示文本



### html5新增属性

**contenteditable**

作用：指定是否可以在浏览器里编辑内容

值：true/false

注意：设置document.designMode ='on'时，页面的任意位置都可以编辑；使用contenteditable ='true'则只对具体元素和其包含的元素起作用

移动端：移动端ios5以及android3之后才支持该属性

例如：

```html
<p contenteditable>
    hello,world
</p>
```

> 此时单击页面就会产生效果

**contextmenu**

作用：跟元素关联的右键菜单

值：`<menu>`元素中唯一ID



**data-***

作用：用于存储页面或应用程序的私有定制数据

注意：属性名不应包含任何大写字母，且在前缀`data-`之后必须有至少一个字符；属性值可以是任意字符串

使用：可以在所有浏览器中使用getAttribute方法来获取`data-*`属性的值，也可以使用javascript中dataset属性访问`data-*`属性的值，不过IE10-浏览器不支持dataset



**draggable(IE8-不支持)**

作用：用户是否可以拖动元素

值：true/false/auto

注意：链接和图像默认是可拖动的



**dropzone(所有浏览器都不支持)**  

作用：规定在拖动被拖动数据时是否进行复制、移动或链接

值：copy拷贝/move移动/link指向原始数据链接



**hidden(IE7-不支持)**

作用：显示或隐藏该元素(与display:none作用一样)

值：hidden="" || hidden= "hidden"



**spellcheck(IE9-不支持)**

作用：规定是否对元素进行拼写和语法检查，对拼写错误的单词会在其下方出现红线

范围：可编辑区域（表单或contenteditable元素）

值：true/false

注意：移动端支持不好



**translate(所有浏览器都不支持)**

作用：规定是否应该翻译元素内容

值：yes/no



## html5的设计原则

实际上，html5并不是由w3c直接制定的，w3c的方向是xhtml2，而不是html5。当xhtml2脱离现实，无法付诸实践时，w3c工作组才将研究方向转向html5。为什么xhtml2从未落到实处？因为它违反了一条设计原理，这条设计原理就是著名的伯斯塔尔法则——发送时要保守；接收时要开放。而在html5设计过程中遵循了一系列原则，才使得html5得以快速推广。



> 避免不必要的复杂性

**html4**

```html
<!DOCTYPE html PUBLIC "-//W3C/DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
```

**html5**

```html
<!DOCTYPE html>
```

**html4**

```html
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
```

**html5**

```html
<meta charset="utf-8">
```



> 支持已有内容

以下四段代码，在xhtml中只有第一段是正确的；而在html5中，所有的都是正确的

```html
<img src="foo" alt="bar" />
<p class="foo">Hello world</p>

<img src="foo" alt="bar">
<p class="foo">Hello world

<IMG SRC="foo" ALT="bar">
<P CLASS="foo">Hello world</P>

<img src=foo alt=bar>
<p class=foo>Hello world</p>
```

> 解决现实问题

在html4中，即使两个块级元素元素有相同的链接地址，也必须分开写，因为内联元素不能包含块级元素

```html
<h2><a href="/path/to/resource">Headline text</a></h2>
<p><a href="/path/to/resource">Paragraph text.</a></p>
```

而在html5中，由于使用了内容模型，`<a>`元素也可以包含块级元素

```html
<a href="/path/to/resource">
    <h2>Headline text</h2>
    <p>Paragraph text.</p>
</a>
```

> 内容模型

html5新增了多个元素，其中包括：section、article、aside和nav，它们代表了一种新的内容模型——给内容分区。以前人们一直都在用div来组织页面中的内容，但与其他类似的元素一样，div本身并没有语义。但section、article、aside和nav实际上是在明确地告诉你——这一块就像文档中的另一个文档一样。位于这些元素中的任何内容，都可以拥有自己的概要、标题，自己的脚部。

> 平稳退化

浏览器在遇到不识别的type值时，会将type的值解释为text

```html
input type="number"
input type="search"
input type="range"
input type="email"
input type="date"
input type="url"
```



## html5标签嵌套规则

在html5中，`<a>`元素的子元素可以是块级元素，这在以前是被认为不符合规则的。本文将详细介绍html5的标签嵌套规则。



### 嵌套规则分类

html5出现之前，经常把元素按照block、inline、inline-block来区分。在html5中，元素不再按照display属性来区分，而是按照[内容模型](http://www.cnblogs.com/xiaohuochai/p/5046584.html)来区分，分为元数据型(metadata content)、区块型(sectioning content)、标题型(heading content)、文档流型(flow content)、语句型(phrasing content)、内嵌型(embedded content)、交互型(interactive content)。元素不属于任何一个类别，被称为穿透的；元素可能属于不止一个类别，称为混合的。



![æ ç­¾åµå¥](./images/HTML_grammar_tagsNesting.png)

**元数据元素**(metadata content)是可以被用于说明其他内容的表现或行为，或者在当前文档和其他文档之间建立联系的元素。

```
base link meta noscript script style template title
```

**流元素**(flow content)是在应用程序和文档的主体部分中使用的大部分元素

```
a abbr address area(如果它是map元素的子元素) article aside audio b bdi bdo blockquote br button canvas cite code data datalist del dfn div dl em embed fieldset figure footer form h1 h2 h3 h4 h5 h6 header hr i iframe img input ins kbd keygen label main map mark math meter nav noscript object ol output p pre progress q ruby s samp script section select small span strong sub sup svg table template textarea time u ul var video wbr text
```

**区块型元素**(sectioning content)是用于定义标题及页脚范围的元素

```
article aside nav section
```

**标题型元素**(heading content)定义一个区块/章节的标题

```html
h1 h2 h3 h4 h5 h6
```

**语句型元素**(phrasing content)是用于标记段落级文本的元素

```
a abbr area (如果它是map元素的子级) audio b bdi bdo br button canvas cite code data datalist del dfn em embed i iframe img input ins kbd keygen label map mark math meter noscript object output progress q ruby s samp script select small span strong sub sup svg template textarea time u var video wbr text
```

**嵌入型元素**(embedded content)是引用或插入到文档中其他资源的元素

```
audio canvas embed iframe img math object svg video
```

**交互型元素**(interactive content)是专门用于与用户交互的元素

```
a audio(如果设置了controls属性) button embed iframe img(如果设置了usemap属性) input(如果type属性不为hidden) keygen label object(如果设置了usemap属性) select textarea video (如果设置了controls属性)
```

### 子元素

【1】子元素是流元素

```
<article>、<section>、<blockquote>、<li>、<dd>、<figcaption>、<div>、<main>、<td>
```

　　【1.1】子元素是流元素，不包括`<main>`元素

```
<aside>、<nav>
```

　　【1.2】子元素是流元素，但不包括`<table>`元素

```
<caption>
```

　　【1.3】子元素是流元素，但不包括`<form>`元素

```
<form>
```

　　【1.4】子元素是流元素，但不包括`<header>`、`<footer>`、`<main>`元素

```
<header>、<footer>、<main>
```

　　【1.5】子元素是流元素，但不包括`<header>`、`<footer>`、区块型元素(sectioning content)、标题型元素(heading content)

```
<dt>、<th>
```

　　【1.6】子元素是流元素，但不包括`<header>`、`<footer>`、`<address>`、区块型元素(sectioning content)、标题型元素(heading content)

```
<address>
```

　　【1.7】子元素是一个`<figcaption>`元素，紧跟着流元素

```
<figure>
```

　　【1.8】子元素是一个`<legend>`元素，紧跟着流元素

```
<filedset>
```

 

【2】子元素是语句型元素

```
<h1>、<h2>、<h3>、<h4>、<h5>、<h6>、<p>、<pre>、<em>、<strong>、<small>、<s>、<cite>、<q>、<abbr>、<data>、<time>、<code>、<var>、<samp></span>、<kbd>、<sub>、<sup>、<i>、<b>、<u>、<mark>、<bdi>、<bdo>、<span>、<input>、<output>、<legend>、<label>
```

　　【2.1】子元素是语句型元素，但不包括和自身相同的元素

```
<dfn>、<progress>、<meter>
```

　　【2.2】子元素是语句型元素，但不包括交互型元素(interactive content)

```
<button>
```

 

【3】子元素是transparent(以它的父元素允许的子元素为准)

```
<ins>、<del>、<map>
```

　　【3.1】子元素是transparent(以它的父元素允许的子元素为准)，但不包括交互型元素(interactive content)

```
<a>
```

　　【3.2】子元素可以没有、可以是`<param>`元素，也可以是transparent(以它的父元素允许的子元素为准)

```
<object></span>
```

 

【4】无子元素

```
<hr>、<br>、<wbr>、<img>、<embed>、<param>、<source>、<track>、<area>、<col>、<keygen>
```

　　【4.1】子元素可以没有、可以是`<li>`元素，也可以是`<script>`、`<template>`元素

```
<ol>、<ul>
```

　　【4.2】子元素可以没有、可以是`<dt>`和`<dd>`元素，也可以是`<script>`、`<template>`元素

```
<dl>
```

　　【4.3】子元素可以没有，可以是`<option>`、`<optgroup>`，也可以是`<script>`、`<template>`元素

```
<select></span>
```

　　【4.4】子元素可以没有，可以是`<option>`，也可以是`<script>`、`<template>`元素

```
<optgroup>
```

　　【4.5】子元素可以没有、可以是`<option>`元素

```
<datalist>
```

　　【4.6】子元素可以没有、也可以是`<track>`元素，也可以是`<source>`元素

```
<audio>、<video>
```

　　【4.7】子元素可以没有，也可以是`<col>`、`<template>`元素

```
<colgroup>
```

　　【4.8】子元素可以没有，可以是`<tr>`，也可以是`<script>`、`<template>`元素

```
<tbody>、<thead>、<tfoot>
```

　　【4.9】子元素可以没有，可以是`<tr>`、`<th>`，也可以是`<script>`、`<template>`元素

```
<tr>
```

 

【5】子元素是`<caption>`、`<colgroup>`、`<thead>`、`<tfoot>`、`<tbody>`，也可以是`<script>`、`<template>`元素

```
<table>
```

 

【6】子元素是文本内容

```
<textarea>
```

　　【6.1】子元素可以没有，也可以是文本内容

```
<option>
```

 

### 总结

  关于每个元素的详细嵌套规则，上部分已经详细介绍。这部分主要对常用标签的嵌套规则进行总结

【1】`<h1>`、`<h2>`、`<h3>`、`<h4>`、`<h5>`、`<h6>`、`<p>`的子元素是语句型元素

【2】`<header>`、`<footer>`不可嵌套`<header>`、`<footer>`

【3】`<a>`的子元素是transparent(以它的父元素允许的子元素为准)，但不包括交互型元素(interactive content)

【4】`<form>`不可嵌套`<form>`

【5】`<button>`子元素是语句型元素，不可嵌套交互型元素(interactive content)

【6】`<caption>`不可嵌套`<table>`

【7】`<dt>`、`<th>`不可嵌套`<header>`、`<footer>`、区块型元素(sectioning content)、标题型元素(heading content)



## html条件注释

 IE条件注释是微软从IE5开始就提供的一种非标准逻辑语句，作用是可以灵活的为不同IE版本浏览器导入不同html元素。很显然这种方法的最大好处就在于属于微软官方给出的兼容解决办法而且还能通过W3C的效验

### 识别IE

  因为从IE10开始，IE浏览器已经不再支持条件注释。所以下面的写法，只能识别IE9-浏览器

  注意：两个--和左中括号[之间不能有空格，否则无效

```
<!--[if IE]>
<div class="box" id="box"></div>
<![endif]-->
```

 

### 识别单一IE

```
6    [if IE 6]
7    [if IE 7]
8    [if IE 8]
9    [if IE 9]
<!--[if IE 7]>
<div class="box" id="box"></div>
<![endif]-->
```

 

### 识别范围IE

```
gt        　大于(greater than)
gte     　　大于等于(greater than or equal)
lt          小于(less than)
lte         小于等于(less than or equal) 
<!--[if lte IE 7]>
<div class="box" id="box"></div>
<![endif]-->
```

 

### 识别非IE

  实际上识别的是IE10+浏览器和其他非IE浏览器

```
<!--[if !IE]>
<div class="box" id="box"></div>
<![endif]-->
```

## html规范

HTML是描述网页结构的超文本标记语言，HTML规范能够使HTML代码风格保持一致，使得HTML更容易理解和维护。本文将详细介绍HTML规范

 

### 整体结构

【页面头部】

  1、文件应以`<!DOCTYPE...>`首行顶格开始，推荐使用`<!DOCTYPE html>`

```
<!DOCTYPE html>
```

  2、必须声明文档的编码charset，且与文件本身编码保持一致，指定字符编码的 `meta` 必须是 `head` 的第一个直接子元素。推荐使用UTF-8编码

```
<meta charset="utf-8">
```

  3、根据页面内容和需求填写适当的keywords和description

```
<meta name="description" content="不超过150个字符">
<meta name="keywords" content="">
```

  4、页面title是不可缺少的一项，`title` 必须作为 `head` 的直接子元素，并紧随 `charset` 声明之后

```
<head>
    <meta charset="UTF-8">
    <title>页面标题</title>
</head>
```

【资源引入】

  1、保证 `favicon` 可访问

```
<link rel="shortcut icon" href="path/to/favicon.ico">
```

  2、引入 `CSS` 和 `JavaScript` 时无须指明 `type` 属性

  3、引入 `CSS` 时必须指明 `rel="stylesheet"`

```
<link rel="stylesheet" href="page.css">
```

  4、使用link将css文件引入，并置于head中；使用script将js文件引入，并置于body底部

  5、移动环境或只针对现代浏览器设计的 Web 应用，如果引用外部资源的 `URL` 协议部分与页面相同，建议省略协议前缀。这是因为使用 `protocol-relative URL` 引入 CSS，在 `IE7/8` 下，会发两次请求。是否使用 `protocol-relative URL` 应充分考虑页面针对的环境

```
<script src="//s1.bdstatic.com/jquery.js"></script>
```

【结构优化】

  1、尽量遵循 HTML 标准和语义，但是不要以牺牲实用性为代价。任何时候都要尽量使用最少的标签并保持最小的复杂度

  2、结构顺序和视觉顺序基本保持一致，按照从上至下、从左到右的视觉顺序书写HTML结构。有时为了便于搜索引擎抓取，也会将重要内容在HTML结构顺序上提前

  3、结构、表现、行为三者分离，避免内联

  4、每一个块级元素都另起一行，每一行都使用Tab缩进对齐（head和body的子元素不需要缩进）。删除冗余的行尾空格

  5、对于内容较为简单的表格，建议将tr写成单行

  6、可以在大的模块之间用空行隔开，使模块更清晰

【语义化】

  浏览器会根据标签的语义给定一个默认的样式。判断网页标签语义化是否良好的一个简单方法：去掉样式，看网页结构是否组织良好有序，是否仍然有很好的可读性

  1、尽可能少地使用无语义标签span和div

  2、在语义不明显，既可以使用p也可以使用div的地方，尽量用p

  3、在既可以使用div也可以使用section的地方，尽量用section

  4、不要使用纯样式标签，如b、u等，而改用CSS设置

 

### 代码格式

【缩进】

  使用2个空格代替1个Tab（大多数编辑器中可设置）

```
<ul>
    <li>first</li>
    <li>second</li>
</ul>
```

【命名】

  1、class 必须单词全字母小写，单词间以 - 分隔

  2、class 必须代表相应模块或部件的内容或功能，不得以样式信息进行命名

```
<!-- good -->
<div class="sidebar"></div>

<!-- bad -->
<div class="left"></div>
```

  3、同一页面，应避免使用相同的 `name` 与 `id。`因为IE7-浏览器会混淆元素的 id 和 name 属性， document.getElementById 可能获得不期望的元素。所以在对元素的 id 与 name 属性的命名需要非常小心

【标签】

  1、标签名必须使用小写字母

  2、对于无需自闭合的标签，不需要自闭合

  3、对 `HTML5` 中规定允许省略的闭合标签，不允许省略闭合标签

  4、`HTML` 标签的使用应该遵循标签的语义，且要符合标签嵌套规则

```
<!-- good -->
<p>Hello StyleGuide!</p>
<!-- bad -->
<P>Hello StyleGuide!</P>

<!-- good -->
<input type="text" name="title">
<!-- bad -->
<input type="text" name="title" </>

<!-- good -->
<ul>
    <li>first</li>
    <li>second</li>
</ul>
<!-- bad -->
<ul>
    <li>first
    <li>second
</ul>
```

【注释】

  采用类似标签闭合的写法，与HTML统一格式；注释文案两头空格，与CSS注释统一格式

  开始注释：（文案两头空格）

  结束注释：（文案前加“/”符号，类似标签的闭合）

  允许只有开始注释

```
<!-- 头部 -->
<div class="g-hd">
    <!-- LOGO -->
    <h1 class="m-logo"><a href="#">LOGO</a></h1>
    <!-- /LOGO -->
    <!-- 导航 -->
    <ul class="m-nav">
        <li><a href="#">NAV1</a></li>
        <li><a href="#">NAV2</a></li>
        <!-- 更多导航项 -->
    </ul>
    <!-- /导航 -->
</div>
<!-- /头部 -->
```

【属性】

  1、属性和值全部小写

  2、属性值必须用双引号包围

  3、布尔类型的属性，建议不添加属性值

  4、自定义属性建议以 `xxx-` 为前缀，推荐使用 `data-`

  5、可以省略style标签和script标签的type属性

```
<!-- good -->
<table cellspacing="0">...</table>
<!-- bad -->
<table cellSpacing="0">...</table>

<!-- good -->
<script src="esl.js"></script>
<!-- bad -->
<script src='esl.js'></script>
<script src=esl.js></script>
```

【属性顺序】

  HTML 属性应该按照特定的顺序出现以保证易读性

```
id
class
name
data-xxx
src, for, type, href
title, alt
aria-xxx, role
```

 

### 特殊元素

【图片】

  1、禁止 `img` 的 `src` 取值为空，否则会导致部分浏览器重新加载一次当前页面

  2、为图片添加 `alt` 属性，提高图片加载失败时的用户体验

  3、避免为 `img` 添加不必要的 `title` 属性，多余的 title 影响看图体验，并且增加了页面尺寸

  4、为图片添加 `width` 和 `height` 属性，以避免页面抖动

```
<img src="#" alt="#" width="#" height="#">
```

  5、有下载需求的图片采用 `img` 标签实现，无下载需求的图片采用 `CSS` 背景图实现

  产品 logo、用户头像、用户产生的图片等有潜在下载需求的图片，以 img 形式实现，能方便用户下载

  无下载需求的图片，比如：icon、背景、代码使用的图片等，尽可能采用 css 背景图实现

【表单】

  1、有文本标题的控件使用 `label` 标签将其与其标题相关联。最好将控件置于 label 内，以减少不必要的 id

```
<label><input type="checkbox" name="confirm" value="on"> 我已确认上述条款</label>
```

  2、使用 `button` 元素时必须指明 `type` 属性值。因为button 元素的默认 type 为 submit，如果被置于 form 元素中，点击后将导致表单提交

```
<button type="submit">提交</button>
<button type="button">取消</button>
```

  3、在针对移动设备开发的页面时，根据内容类型指定输入框的 `type` 属性，能获得友好的输入体验

```
<input type="date">
```

【多媒体】

  1、在支持 `HTML5` 的浏览器中优先使用 `audio` 和 `video` 标签来定义音视频元素，并使用退化到插件的方式来对多浏览器进行支持

```
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    <source src="audio.ogg" type="audio/ogg">
    <object width="100" height="50" data="audio.mp3">
        <embed width="100" height="50" src="audio.swf">
    </object>
</audio>

<video width="100" height="50" controls>
    <source src="video.mp4" type="video/mp4">
    <source src="video.ogg" type="video/ogg">
    <object width="100" height="50" data="video.mp4">
        <embed width="100" height="50" src="video.swf">
    </object>
</video>
```

  2、只在必要的时候开启音视频的自动播放

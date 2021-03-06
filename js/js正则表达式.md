## 正则的概念
		正则表达式是对字符串操作的一种逻辑公式，就是用事先定义好的一些特定字符、及这些特定字符的组
	合，组成一个“规则字符串”，这个“规则字符串”用来表达对字符串的一种过滤逻辑。
	
	给定一个正则表达式和另一个字符串，我们可以达到如下的目的：
		1. 给定的字符串是否符合正则表达式的过滤逻辑（称作“匹配”）；
		2. 可以通过正则表达式，从字符串中获取我们想要的特定部分。
	
	正则表达式的特点是：
		1. 灵活性、逻辑性和功能性非常的强；
		2. 可以迅速地用极简单的方式达到字符串的复杂控制。
		3. 对于刚接触的人来说，比较晦涩难懂。
		
		由于正则表达式主要应用对象是文本，因此它在各种文本编辑器场合都有应用，小到著名编辑器
	EditPlus，大到Microsoft Word、Visual Studio等大型编辑器，都可以使用正则表达式来处理文本内容。

## RegExp 对象
	1.创建（定义）正则表达式
		格式： 
			new RegExp(pattern, attributes);
			pattern：模式字符串(规则字符串)
			attributes：字符串，可选。包含属性 "g"、"i" 和 "m"，分别用于指定全局匹配、区分大小
		写的匹配和多行匹配。ECMAScript 标准化之前，不支持 m 属性。如果 pattern 是正则表达式，而不是字符串，则必须省略该参数
	
	例如：
		var reg= new RegExp(‘study’); //表示含有study，（默认区分大小写）
		var reg = new RegExp('study', 'ig');
		其中i 表示忽略大小写，g 表示全局匹配,
	
	2.使用常量方式直接声明(//)
		如：var reg = /study/;
		等价于：var reg= new RegExp('study');
		等价于：var reg= new RegExp(/study/);

## RegExp 对象
	属性:
		global RegExp对象是否具有标志 g。 全局
		ignoreCase RegExp对象是否具有标志 i。 忽略大小写
		source 正则表达式的源文本。
		Multiline RegExp 对象是否具有标志 m。 不只匹配一行。
	
	方法:
		exec(字符串) 检索字符串中指定的值。返回找到的值，如果没有匹配到，则返回null。
		test (字符串) 检索字符串中指定的值。返回 true 或 false。
		使用RegExp对象的字符串函数
		var pattern = /good/ig; //全局搜索
		var str = 'good good study!，day day up!';
	
	1.使用 match 方法获取获取匹配数组a
		alert(str.match(pattern)); //匹配到两个 good,good
	
	2.使用 search 来查找匹配数据
		alert(str.search(pattern)); //查找到返回位置，否则返回-1
	
	3.使用 replace 替换匹配到的数据（找到并替换）
		alert(str.replace(pattern, 'hard')); //将Good替换成了hard
	
	4.使用 split 拆分成字符串数组,
	 var arr = str.split(pattern); //将按空格拆开字符串成数组

## 正则表达式的特殊字符
	^ 匹配一行的开头，/^a/匹配"abc"，而不匹配“bca“
	$ 匹配一行的结尾，/a$/匹配“bca"，而不匹配"abc"
	. 匹配单个字符，除了换行和行结束符，等价于[^\n]
	* 匹配前面元字符0次或多次，/ba*/将匹配b,ba,baa,baaa
	+ 匹配前面元字符1次或多次，/ba+/将匹配ba,baa,baaa
	? 匹配前面元字符0次或1次，/ba?/将匹配b,ba
	x|y 匹配x或y ,/a|b/ 将匹配只要出现a或者b的字符串，不含a与b的不匹配
	{n} 精确匹配n次 ，/d{4}/ 将匹配，出现连续4个d的字符串
	{n,} 匹配n次以上 ，/d{4,}/将匹配，出现连续4个及其以上多个d的字符串
	{n,m} 匹配n-m次，/d{4,6}/将匹配，出现连续4到6个d的字符串
	[xyz] 匹配这个集合中的任一一个字符，如：[a-z] 表示小写a到小写z范围的字符。
	[^xyz] 不匹配这个集合的任何一个字符 ，同样可以写范围，如：[^a-z]
	(red|blue|green) 将一些正则匹配规则合成一个小组。
	\d 匹配一个数字字符，/\d/ 等价于 /[0-9]/
	\D 匹配一个非数字字符，/\D/ 等价于 /[^0-9]/
	\w 匹配一个可以组成单词(变量)的字符(包括字母，数字，下划线)等价于[a-zA-Z0-9_]
	\W 匹配一个不可以组成单词的字符

## 正则表达式的特殊字符
	\n 匹配一个换行符
	\f 匹配换页符。
	\r 匹配一个回车符
	\t 匹配一个制表符
	\v 匹配一个重直制表符
	\s 匹配一个空白字符，包括\n,\r,\f,\t,\v等
	\S 匹配一个非空白字符，等于/[^\n\f\r\t\v]/
	\b 匹配一个单词的边界 (单词是以空格分割的)
	\B 匹配一个单词的非边界
	\0 匹配NUL 字符。
	\ddd 匹配以八进制数 ddd 规定的字符。 Ru:var reg = /\141/; 等价于 var reg = /a/;
	\xdd 匹配以十六进制数 dd 规定的字符。
	\uxxxx 匹配以十六进制数 xxxx 规定的 Unicode 字符。

## 直接量字符（转义字符）
	\f 换页符
	\n 换行符
	\r 回车
	\t 制表符
	\v 垂直制表符
	\/ 一个 / 直接量
	\\ 一个 \ 直接量
	\. 一个 . 直接量
	\* 一个 * 直接量
	\+ 一个 + 直接量
	\? 一个 ? 直接量
	\| 一个 | 直接量
	\( 一个 ( 直接量
	\) 一个 ) 直接量
	\[ 一个 [ 直接量
	\] 一个 ] 直接量
	\{ 一个 { 直接量
	\} 一个 } 直接量
	\- 一个-直接量

## 量词
	c{n} 匹配包含 n 个 c 的序列的字符串。
	c{m,n} 匹配包含 m 到 n 个 c 的序列的字符串。
	c{n,} 匹配包含至少 n 个 c 的序列的字符串。
	c+ 匹配任何包含至少一个 c 的字符串，等价于c{1,} 。
	c* 匹配任何包含零个或多个 c 的字符串，等价于c{0,}
	c? 匹配任何包含零个或一个 c 的字符串，等价于 c{0, 1}
	c$ 匹配任何结尾为 c 的字符串。
	^c 匹配任何开头为 c 的字符串。
	?=c 匹配任何其后紧接指定字符串 c 的字符串。
	对其后紧跟 "all" 的 "is" 进行全局搜索.
	var str="Is this all there is"; var patt1=/is(?= all)/g;
	?!c 匹配任何其后没有紧接指定字符串 c 的字符串。
	对其后没有紧跟 "all" 的 "is" 进行全局搜索：
	var str="Is this all there is"; var patt1=/is(?! all)/gi; 

## 常见正则
	检查邮政编码 //共 6 位数字，第一位不能为 0
	/^[1-9]\d{5}$/
	检查文件压缩包 //xxx.zip\xxx.gz\xxx.rar
	/^\w+\.(zip|gz|rar)$/
	删除多余空格
	str.replace(/\s+/,'');
	删除首尾空格
	str.replace(/^\s+/,'');
	str.replace(/\s+$/,'');
	电子邮件( xxxxx @ xxxx(.xxxx)+) //770107@qq.com; 770107@qq.com.cn
	/^\w+@\w+(\.\w+)+$/
	手机号
	/^1\d{10}$/

### 示列"常用的正则"

```html
<!doctype html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	用户名：<input id="userId" type="text"/><span></span><br/>
	邮政编码<input id="postId" type="text"/><span></span><br/>
	邮箱<input id="emailId" type="text"/><span></span><br/>
	手机号码：<input id="phoneId" type="text"/><span></span><br/>
	身份证号码：<input id="cardId" type="text"/><span></span><br/>
	出生日期：<input id="birthdayId" type="text"/><span></span><br/>
	ip：<input id="ipId" type="text"/><span></span><br/>
</body>
</html>
<script type="text/javascript" src="js/tools.js"></script>
<script type="text/javascript">

//总结：
//正则的规则：
//1、限定字符
//2、限定数量
//3、限定位置

window.onload = function () {

	$("#userId").onblur = function(){
		 var reg = /^[a-zA-Z_][a-zA-Z0-9_]{5,15}$/;//一共长度是6-16位，由数字字母下划线构成，但是数字不能开头
    	if(reg.test(this.value)==true){
    		this.nextElementSibling.innerHTML = "√";
    	}else{
    		this.nextElementSibling.innerHTML = "×";
    	}
	}

	$("#postId").onblur = function(){
		//共 6 位数字，第一位不能为 0
		 var reg = /^[1-9]\d{5}$/;
		if(reg.test(this.value)==true){
    		this.nextElementSibling.innerHTML = "√";
    	}else{
    		this.nextElementSibling.innerHTML = "×";
    	}
	}

	
	$("#emailId").onblur = function(){
		//电子邮箱的规则：至少3个数字字母下划线@至少2个数字字母下划线.(com|cn|net|com.cn)
	
		var reg = /^\w{3,}@\w{2,}\.(com|cn|net|com.cn)$/;
		if(reg.test(this.value)==true){
    		this.nextElementSibling.innerHTML = "√";
    	}else{
    		this.nextElementSibling.innerHTML = "×";
    	}

	}

	$("#phoneId").onblur = function(){
		//手机的规则：11位数字，1开头

		var reg = /^1\d{10}$/;
		if(reg.test(this.value)==true){
    		this.nextElementSibling.innerHTML = "√";
    	}else{
    		this.nextElementSibling.innerHTML = "×";
    	}
	}


	$("#cardId").onblur = function(){
		//身份证的规则：18位，前17位是数字，不能以0开头，最后一位是数字或者X
		var reg = /^[1-9]\d{16}(\d|X)$/i;
		if(reg.test(this.value)==true){
    		this.nextElementSibling.innerHTML = "√";
    	}else{
    		this.nextElementSibling.innerHTML = "×";
    	}
	}


	$("#birthdayId").onblur = function(){
		//日期的规则：四位数字(-./)两位数字(-./)两位数字
		// var reg = /^\d{4}[-\./]\d{2}[-\./]\d{2}$/i;
		//var reg = /^\d{4}[\-\./](0[1-9]|1[0-2])[\-\./]\d{2}$/i;
		
		var reg = /^(\d{4}\-(0[1-9]|1[0-2])\-\d{2}|\d{4}\.(0[1-9]|1[0-2])\.\d{2}|\d{4}\.(0[1-9]|1[0-2])\.\d{2})$/i;

		if(reg.test(this.value)==true){
    		this.nextElementSibling.innerHTML = "√";
    	}else{
    		this.nextElementSibling.innerHTML = "×";
    	}
	}


	$("#ipId").onblur = function(){
		//ipV4的规则：0-255.0-255.0-255.0-255
		//0-255   
		// 一位 \d     5.12.3.1
		// 两位 [1-9]\d
		// 三位 
		// 1打头  1\d{2}
		// 2打头  2[0-4]\d
		// 25打头  25[0-5]
		var reg = /^((\d|[1-9]\d|1\d{2}|2[0-4]\d|25[0-5])\.){3}(\d|[1-9]\d|1\d{2}|2[0-4]\d|25[0-5])$/i;

		if(reg.test(this.value)==true){
    		this.nextElementSibling.innerHTML = "√";
    	}else{
    		this.nextElementSibling.innerHTML = "×";
    	}

	}
}


function $(str){
	if(str.charAt(0)=="#"){
		return document.getElementById(str.substring(1));
	}else if(str.charAt(0)=="."){
		return document.getElementsByClassName(str.substring(1));
	}else{
		return document.getElementsByTagName(str);
	}
}	
</script>
```

### 示列"封装正则"

```html
//正则验证的封装
//参数：
//验证的类型
//验证的字符串
//返回值：true：表示合法；false：不合法

var str="hello";

// check("email",str);
// check("card",str);
// check("phone",str);

function check(type,str) {
	switch(type){
		case "email":var reg = /^\w{3,}@\w{2,}\.(com|cn|net|com.cn)$/;break;
		case "phone": var reg = /^1\d{10}$/;break;
		case "card":var reg = /^[1-9]\d{16}(\d|X)$/i;break;
		default:;
	}

	return reg.test(str);
}
```

​	
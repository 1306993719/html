## 严格模式
		HTML_严格模式与混杂模式
	Doctype可声明三种DTD类型，分别表示严格版本、过渡版本以及基于框架的 HTML 文档。
	当浏览器厂商开始创建与标准兼容的浏览器时，他们希望确保向后兼容性。为了实现这一点，他们
	创建了两种呈现模式：
		标准模式和混杂模式
			在标准模式中，又称严格模式，是指浏览器按照 W3C 标准解析代码
			在混杂模式中，页面以一种比较宽松的向后兼容的方式显示。混杂模式通常模拟老式浏览器的
			行为以防止老站点无法工作。
	浏览器根据DOCTYPE是否存在以及使用的哪种DTD来选择要使用的呈现方法。
	如果XHTML、HTML 4.01文档包含形式完整的DOCTYPE，那么它一般以标准模式呈现。
	包含过渡DTD和URI的DOCTYPE也导致页面以标准模式呈现，但是有过渡DTD而没有URI会导致页面
	以混杂模式呈现。
	
	DOCTYPE不存在或形式不正确会导致HTML和XHTML文档以混杂模式呈现。
	html5既然没有DTD，也就没有严格模式与宽松模式的区别，html5有相对宽松的语法，实现时，已经尽可
	能大的实现了向后兼容。

### 严格模式目的
	消除JS语法不合理、不严谨减少怪异行为
	消除代码不安全之处，保证代码运行安全
	提高编译运行效率
	为将来新版本JS做铺垫
	
	语法：
		“use strict”
		
	浏览器支持：
		IE10+ firefox 4+ Safari 5.1+ Chrome

## ES5新增的数值的方法
	indexOf
	forEach()
	filter()
	Map()

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<input type="button" value="  测试  " onclick ="testf()" />			
	</body>
</html>
<script type="text/javascript">
//EcmaScript:简称ES，以前都是ES3的。
//今天看ES5新增的数组方法。
// indexOf
// forEach()
// filter()
// Map()
function testf() {
	//1、indexOf(); 返回一个数在数组中的下标
	// var arr=[12,23,34,45];
	// console.log(arr.indexOf(34));//2
	// console.log(arr.indexOf(100));//-1

	//2、forEach(): 会修改原始数组,好处：不用程序员再写循环语句
	// var arr=[12,23,34,45];
	// arr.forEach(alert);//针对数组中的每个元素进行alert。

	// for(var i in arr){
	// 	alert(arr[i]);
	// }

	// var arr=[12,23,34,45];
	// arr.forEach(arrInc);//把数组arr的每个元素做arrInc处理
	// console.log(arr);

	// arr.forEach(arr13);
	// // for(var i in arr){
	// // 	arr[i] = arr[i]*1.3;
	// // }
	// console.log(arr);
	
	//3、filter();过滤，不会修改原始数组，而是产生新的数组
	// var arr=[-12,23,-34,45,100,-21];
	// var arr1 = arr.filter(gtZero);//把arr里的每个元素做大于0的比较，留下大于0的，放在arr1数组里。
	// console.log(arr);
	// console.log(arr1);

	//4、map();不会修改原始数组，而是产生新的数组
	var arr=[12,23,34,45];
	var arr1 = arr.map(mySqr);
	console.log(arr);
	console.log(arr1);

}

//arrInc：所做处理就是给元素加1
//num：数组元素本身
//index：下标
//arr：是数组本身
function arrInc(num,index,arr){
	arr[index] = num+1;
}

function arr13(num,index,arr){
	// arr[index] = num*1.3;
	arr[index] = arr[index]*1.3;
}

//num：是数组的元素本身
function gtZero(num){
	return num>0;
}

//平方处理
//num:是数组的元素
function mySqr(num){
	return num*num;
}
</script>
```

## 字符串的定义和创建
	字符串就是一串字符，由双（单）引号括起来。字符串是 JavaScript 的一种基本的数据类型。
		
	1、var str=‘亲’； 基本类型
		定义一个字符串变量str，内容为‘亲’
		
	2、var str = new String(“hello”); 引用类型
		定义一个字符串变量str，内容为hello，
		注意此刻str为object(对象)类型
		用new产生的变量都是引用类型的变量，也叫对象。

### 字符串的官方函数
	字符串的函数（方法）--字符串的获取方法:
		charAt(3) //获取下标为3的字符
		charCodeAt(3) //获取下标为3的字符的编码
		fromCharCode(94) //编码转换成字符
	字符串的查找方法:
		indexOf("abc") 查找字符串第一次出现的位置
		lastIndexOf("abc") 查找字符串最后一次出现的位置 如果没找到 返回-1

		
	substring() 提取字符串中两个指定的索引号之间的字符。 
	charCodeAt() 返回在指定的位置的字符的 Unicode 编码。 
	fromCharCode() 从字符编码创建一个字符串。

	slice() 提取字符串的片断，并在新的字符串中返回被提取的部分
	split() 把字符串分割为字符串数组。 
	
	
	match() 找到一个或多个正则表达式的匹配。
	search() 检索与正则表达式相匹配的值。 
	replace() 替换与正则表达式匹配的子串。

	-----------------------------------

	concat() 连接字符串。  
	substr() 从起始索引号提取字符串中指定数目的字符。 
	toLowerCase() 把字符串转换为小写。 
	toUpperCase() 把字符串转换为大写。

## 字符编码

	ASCII（美国信息交换标准代码）是基于拉丁字母的一套电脑编码系统，主要用于显示现代英语和其他西欧语言。
	GBK 共收录了21003个汉字，英文使用单字节编码，兼容ASCII编码，中文部分采用双字节编码。
	Unicode为每种语言中的每个字符设定了统一并且唯一的二进制编码，以满足跨语言、跨平台进行文本转换、处理的要求。
	UTF-8是一种针对Unicode的可变长度字符编码。用在网页上可以统一页面显示中文简体繁体及其它语言。
	
	ASCII码（国际标准信息交换码），给键盘上的每个键（字符）分别对应一个数字，这个数字就是编码。
	a 97  
	b 98
	A 65 
	 "0" 48
	有了ASCII码计算机就能识别英文了
	一个字节（256个数字）够了
	
	GB2312码: 
		简体中文编码，把常见的简体字（3-4000），每个字对应一个编码；
		两个字节（65536个数字）够用
	
	GBK码: 
		K:kuo 扩，扩展码，上万的字。
		两个字节（65536个数字）够用
		
	big-5码:
		繁体字;
		
	unicode码：
		把世界上所有国家和地区的文字收录起来，统一进行编码。就不会乱码，这是一种编码思路
		unicoede编码时，充分考虑到了扩展性，把属于ASCII码里的字符，沿用原来的编码。
		utf-8:是unicode编码的具体解决方案
		utf-16:是unicode编码的具体解决方案
		JavaScript用的是utf-16的编码


	-------------计算机的计量单位----------------
	1、位 bit 位就是数位，（二进制位）
	2、字节 byte 简称B = 8bit （8位二进制） = 2^8（0-2^7-1） = 256个数字； 
		 1字节= 256个（0-255）
		 2字节= 65536个（0-65535）
	3、千字节 KB = 1024B
	4、兆  MB  = 1024KB
	5、G（GB）  = 1024MB
	6、T（TB）  = 1024GB

## ==与===的区别
	===(恒等)：
	1、如果类型不同，就[不相等]
	2、如果两个都是数值，并且是同一个值，那么[相等]。
	3、如果两个都是字符串，每个位置的字符都一样，那么[相等]；否则[不相等]
	4、如果两个值都是true，或者都是false，那么[相等]。
	5、如果两个值都引用同一个对象或函数，那么[相等]；否则[不相等]。
	6、如果两个值都是null，或者都是undefined，那么[相等]。
	
	==(等同):
	1、如果两个值类型相同，进行 === 比较。
	2、如果两个值类型不同，他们可能相等。根据下面规则进行类型转换再比较
	a、如果一个是null、一个是undefined，那么[相等]。
	b、如果一个是字符串，一个是数值，把字符串转换成数值再进行比较。
	c、如果任一值是 true，把它转换成 1 再比较；如果任一值是 false，把它转换成 0 再比较。
	d、任何其他组合，都[不相等]。
	
	等同：
	如果任一值是 true，把它转换成 1 再比较；如果任一值是 false，把它转换成 0 再比较。
		console.log(true==1);//true
		console.log(true==2);//false
		console.log(false==0);//true
		console.log(false==-1);//false


​	
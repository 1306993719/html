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
		
## 字符编码
	ASCII（美国信息交换标准代码）是基于拉丁字母的一套电脑编码系统，主要用于显示现代英语和其他西欧语言。
	GBK 共收录了21003个汉字，英文使用单字节编码，兼容ASCII编码，中文部分采用双字节编码。
	Unicode为每种语言中的每个字符设定了统一并且唯一的二进制编码，以满足跨语言、跨平台进行文本转换、处理的要求。
	UTF-8是一种针对Unicode的可变长度字符编码。用在网页上可以统一页面显示中文简体繁体及其它语言。

	
		
	
	
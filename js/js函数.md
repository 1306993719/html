# 函数

## 函数的概念
	函数就是把完成特定功能的一段代码抽象出来，使之成为程序中的一个独立实体，起个名字（函数名）。可以在同一个
	程序或其他程序中多次重复使用（通过函数名调用）。
	注：
		编写好的函数代码只有通过调用才会执行，不调用的时候不会执行。
		
	函数的作用（好处）：
		1.使程序变得更简短而清晰
		2.有利于程序维护
		3.可以提高程序开发的效率 
		4.提高了代码的重用性(复用性)

## 函数的语法
	1.定义函数（声明函数）
		function 函数名([参数列表]){
			函数体
		[return 值]
	}
	
	2.调用函数
		函数名([参数列表]);
	
	要点：
		没有参数和返回值的函数，就像是在原来实现某功
		能的代码上加了盖。
		函数初学者，函数声明不要写在别的函数内。

## 有参函数
	参数：就是写在函数名后面圆括号里的变量。
	形参：形式参数；定义函数时的参数
	实参：实际参数；调用函数时的参数
	
	调用函数时，是把实参的值传给了形参。
	
	调用函数
	sumN(3);	//3是实参
	sumN(7);	//7是实参
	sumN(10);	//10是实参
	
	定义函数
	function sumN(n) {		//n是形参
	var sum = 0;		//保存求和的结果
	var add = 1;
	
	while(add<=100){
		if(add%n==0){
			sum = sum +add;//age = age+1;
		}
		add=add+1; 
	}
	console.log(sum);	
	}	

### 有参函数示列

```html
<!doctype html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title></title>
	<style type="text/css">
	</style>
</head>
<body>

</body>
</html>
<script type="text/javascript" >
//函数是完成一件事情
//形参：表示函数的已知条件

//n1和n2就是形参
cal(3,5,'+');

function cal(n1,n2,oper){
	switch(oper){
		case '+':console.log(n1+n2);break;
		case '-':console.log(n1-n2);break;
		case '*':console.log(n1*n2);break;
		case '/':if(n2==0){
					console.log('除数不能为0');
				}else{
					console.log(n1/n2);
				}
				break;
		case '%':if(n2==0){
					console.log('除数不能为0');
				}else{
					console.log(n1%n2);
				}
				break;
		default:;
	}
}
</script>
```

```html
<!doctype html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title></title>
</head>
<body>

</body>
</html>
<script type="text/javascript" >

// var n1=20
// var n2=12
// var n3 = 2

//   n2   n1  

sort(20,10,5);

function sort(n1,n2,n3){
	if(n1<n2){
		if(n3<n1){
			console.log(n3,n1,n2);
		}else if(n3>n1 && n3<n2){
			console.log(n1,n3,n2);
		}else{
			console.log(n1,n2,n3);
		}
	}else{//n2   n1
		if(n3<n2){
			console.log(n3,n2,n1);
		}else if(n3>n2 && n3<n1){
			console.log(n2,n3,n1);
		}else{
			console.log(n2,n1,n3);
		}
	}
}
</script>
```

## 函数返回值
	函数的返回值：就是函数运算结果。

### 函数返回值示列

```html
<!doctype html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title></title>
	<style type="text/css">
	</style>
</head>
<body>
	请输入一个数：<input id="num" type="text" >
	<input type="button" value="是不是素数" onclick="testf()" />
	<input id="result" type="text" >
	
</body>
</html>
<script type="text/javascript" >
//函数的返回值：就是函数运算结果。

function testf(){
	//1、获取用户的输入
	var num = Number(document.getElementById("num").value);
	// var t = Math.pow(5,3);
	// if(Math.pow(5,3)>20){
	// }
	
	//2、逻辑判断
	if(isPrimer(num)==true){
		//3、输出
		document.getElementById("result").value = num+"是素数";
	}else{
		//3、输出
		document.getElementById("result").value = num+"不是素数";
	}
}
//功能：判断一个数是不是素数(只能被1和它自身整除，
//即就是：除了1和它自身外，所有的数都不能整除它)
//参数：一个数
//返回值：true：表示是素数；false：不是素数；

//定义（声明）函数
function isPrimer(num) {//9

	for(var i=2;i<=num-1;i++){//2
		if(num%i==0){
			break;
		}
	}
	// console.log(i);
	if(i==num){
		return true;
	}else{
		return false;
	}
}
</script>
```
### Math.random

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
<script type="text/javascript" >
function testf(){
	//获取随机数：Math.random()// 0-1的小数，不含1
	/*
	var num = Math.random();
	console.log(num);
	*/

	//得到一个0-10(不含)之间的随机数

	// var num = parseInt(Math.random()*10);
	// console.log(num);

	//得到一个0-10(含)之间的随机数

	// var num = parseInt(Math.random()*11);
	// console.log(num);

	//得到 2-8（不含）之间的随机数

	var num = parseInt(Math.random()*6);//0-5;
	num = num+2;
	console.log(num);
}
</script>
```

### 示列"四位的数字验证码"

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<input type="button" value="  验证码  " onclick ="testf()" />
		<input type="text" id="txt" />
	</body>
</html>
<script type="text/javascript" >
function testf(){
	document.getElementById("txt").value = checkMa(6);
}
//功能：n位的数字验证码
//参数：n
//返回值：验证码

function checkMa(n){
	// 4
	// 10000
	// 0.00518972323

	var str="";
	for(var i=0;i<n;i++){
		str = str + parseInt(Math.random()*10);
	}		
	return str;
}
</script>
```

## 封装函数
	定义函数的注意点：
		1.形参，不要在函数内部重新定义
		2.函数内部尽量不要出现输出语句（alert，document.write）
		3.return后面只能出现一个值（即函数只能返回一个值） 

### 示列

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		
	</head>
	<body>
	请输入数字：<input type="text" id="txt" />	
	<input type="button" value="  文本框中是数字吗  " onclick ="testf()" />
	</body>
</html>
<script type="text/javascript" >


//功能：判断一个年份是不是闰年
//参数：年份
//返回值：true：是；false：否

// isLeapYear(12);
function isLeapYear(num1) {
	if((num1%4==0 && num1%100!=0) || (num1%400==0)){
		return true;
	}else{
		return false;
	}
}

    
//功能：已知x求y
//参数：就是已知条件，x
//返回值：就是结果，y

// var t = getYByX(5);

function getYByX(x) {
	
	if(x<1){
		y = x;
	}else if(x<10){
		y = 2*x+1;
	}else{
		y = 5*x-17;
	}
	//3、输出y
	return y;
}	

//根据数字（0-6），得到汉字的星期
function toWeek(num) {

	//2、逻辑
	var result = "";
	switch(num){
		case 0:result="星期天";break;
		case 1:result="星期一";break;
		case 2:result="星期二";break;
		case 3:result="星期三";break;
		case 4:result="星期四";break;
		case 5:result="星期五";break;
		case 6:result="星期六";break;
		default:result="亲，您又可胡输入呢";break;
	}
	//3、输出y
	return result;
}	

    
    
//功能：根据身高，体重判断胖瘦
//参数：身高，体重
//返回值：1：胖；0：正常：-1：瘦

function bmi(height,weight) {	
	//2、逻辑
	var result = "";
	var standardWeight = height-108;

	if(weight<standardWeight-5){
		result = "-1";
	}else if(weight>standardWeight+5){
		result = "1";
	}else{
		result = "0";
	}
	//3、输出
	return result;
}	

 
    
//功能：求1-n之间m的倍数的数之和
//参数：最大数 n；除数m
//返回值：和
function sumNAndM(n,m){
	var sum = 0;//保存求和的结果
	var add = 1;

	while(add<=n){
		if(add%m==0){
			sum = sum +add;
		}
		add=add+1; 
	}
	return sum;
}
</script>
```

## JS的编译和执行
	JS的编译和执行：
		javascript代码在运行时有预编译和执行两个阶段，在预编译阶段会对函数和变量进行处理，对所有的
		声明变量会赋值为undefined，对所有的声明函数也会赋值为函数的定义。
		在执行阶段会按照代码顺序，一行行的翻译并执行代码。
		
	从开发到运行的过程：
		编辑代码(自然语言源代码)-----(预编译)---->编译代码（机器语言0和1）----->执行

## 变量的作用域 
	变量的作用域：
		就是变量起作用的范围。或者说有效范围。
		
	局部变量
		局部变量就是定义在函数内部的变量，这个变量只能在函数内部使用，即作用域范围只是函数内部，
	另外，形参也是局部变量。
	
	全局变量
		全局变量就是定义在函数外部的变量，这个变量在任何函数中都有效，即作用域范围是当前文件的
	任何地方。不但在任何函数中都可以使用，而且值是共享。即A函数改变值后，B函数拿到的就是改后
	的值。就像共享单车一样。

### 示列"全局和局部重名"

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<input  type="button" value="测试" onclick="testf()" >
	</body>
</html>
<script type="text/javascript" >

function testf(){
	func1();
	func2();
}	

var age =100;//全局变量，全局变量的值是共享

function func1() {
	var age = 350;//局部变量
	alert(age);//350
}

function func2() {
	alert(age);//100，全局变量
}
</script>
```



## 变量的声明提升

	变量的声明提升：
		变量声明总是会被解释器悄悄地被“提升”到方法体的最顶部
		请注意，变量赋值并没有被提升，只是声明被提升了。

### 示列"当全局和局部重名时碰到声明提升"	

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<input  type="button" value="测试" onclick="testf()" >
	</body>
</html>
<script type="text/javascript" >

function testf(){
	func1();
	func2();
}	
var age =100;//全局变量，全局变量的值是共享

//以下代码，
function func1() {
	alert(age);//这个是局部变量 undefined; 
	var age = 350;
}
//经过预编译后
function func1() {
	var age;
	alert(age);//这个是局部变量 undefined; 
	age = 350;
}
function func2() {
	alert(age);//100
}
</script>
```

## 事件调用函数
	事件调用函数： 
		我们把事件和自定义函数建立起对应关系，当事件发生时就去调用我们的函数。
	
	我们已经学习了onclick事件，还有onload, onfocus、onblur等等。
		onload:标签（页面）加载完成(页面完全打开)
		onfocus:获得焦点（简单理解为，光标进入）
		onblur:失去焦点（简单理解为，光标离开）

### 示列"onfocus与onblur"

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<input id="txt" type="text" value="请输入电影名" onblur="resetText()" onfocus="clearText()" />
		<input  type="button" value="搜索"  >
	</body>
</html>
<script type="text/javascript" >

function clearText() {
	if(document.getElementById("txt").value=="请输入电影名"){
		document.getElementById("txt").value = "";
	}
}
function resetText(){
	if(document.getElementById("txt").value==""){
		document.getElementById("txt").value = "请输入电影名";	
	}
}
</script>
```

## 递归函数 
	JS函数可以相互调用，嵌套调用
	JS函数也能调用自己，调用自己的函数叫做递归函数，递归函数就是特殊的嵌套调用函数。

### 示列"斐波那契数列"

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		请输入一个数:<input type="text" id="txtId" >
		<input  type="button" value="求斐波那契数" onclick="testf()" >
	</body>
</html>
<script type="text/javascript" >

function testf(){
	var num = Number(document.getElementById("txtId").value);

	var temp = fbnq(num);

	console.log(temp);
}	
/*
              n1     n2    n3
 n1     n2    n3
  1     1     2      3      5     8     13     21
        n1    n2     n3
*/
//求第n个斐波那契数列的数

function fbnq(n){
	if(n==1 || n==2){
		return 1;
	}
	var n1=1;
	var n2=1;
	var n3;
	for(var i=3;i<=n;i++){
		n3 = n1+n2;
		n1 = n2;
		n2 = n3;
	}
	return n3;
}

/*
//递归做斐波那契数列
function fbnq(n){
	if(n==1 || n==2){
		return 1;
	}
	return fbnq(n-1)+fbnq(n-2);
}
*/
</script>
```



​	
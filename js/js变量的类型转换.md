# js的类型转换

## 隐式（自动）转换
	不同的数据类型参与表达式运算过程时将会转换为同一类型进行运算
	
	字符串与数值类型运算的隐式转换规则：
		1.字符串加数字,数字就会转成字符串。
		2.数字减字符串，字符串转成数字。如果字符串不是纯数字就会转成NaN。字符串减数字也一样。两
		个字符串相减也先转成数字。
		3.乘，除，大于，小于跟减的转换也是一样。
		
	一.字符串与数字进行加法运算，把数字转成字符串
	
		var age = 25;
		var str ='我今年'+age; //浏览器会先把age转成字符串。
		alert(str);
	
	二.字符串与数字进行减法运算，把字符串转成数字
	
		var str1 = '12';//字符串类型
		var num = 5;//number类型
		var t = str1-num;
		alert(t);
	
		var str1 = 'a';//字符串类型
		var num = 5;//number类型
		var t = str1-num;//str1转成数字的结果是NaN（not a number）
		alert(t);

## 显示（手动）转换
	字符串转数值：
		parseInt()、parseFloat()、Number()
	数值转字符串:
		toString()
		
	1、parseInt():把字符串转成整型，int：是整型的意思
		var str1 = '12';
		var str2 = '8';
		加号 有两个意思，在数字运算中表示加法；在字符串里表示连接
		var s = parseInt(str1)+parseInt(str2);
		alert(s);
	
		var s = str1-str2;//减法不用强制转换，因为，减法只表示减法
		alert(s);
	
	2、parseFloat();//把字符串转成浮点型;float:浮点型，就是小数。
		var str1='12.5';
		var str2 = 3.2;
		var s = parseFloat(str1)+str2;
		alert(s);
	
	3、Number();//把字符串转成数字型（包括整型和浮点型）
		var str1='12.5';
		var str2 = 3.3;
		var s = Number(str1)+str2;
		alert(s);
	
		var str1 = '12';
		var str2 = '8';
		var s = Number(str1)+Number(str2);
		alert(s);

##  parseInt(),parseFloat(),Number() 的区别？
	答：
	1.
		parseInt()字符串转换成整型，
		parseFloat()字符串转换成浮点型，
		Number()字符串转换成数字型;
	
	2.
		Number():看的是整体，只要字符串内的内容不是合法的数字，则结果为NaN；否则，就会正常转换为数字类型。
		parseInt()：如果遇到小数点或者其它非数字字符或结尾，那么就把前面的内容正常转换为数字
		parseFloat()：如果遇到第二个小数点或者其它非数字字符或结尾，那么就把前面的内容正常转换为数字
		parseInt() 和 parseFloat()的转换规则比较接近(类似)从前朝后，如果第一个字符是非数字，那么，结果为NaN；如果第一个字符是数字

## 四舍五入、乘方
	1.四舍五入取整
		var num1=Math.round(23.49);
		alert(num1);//结果23
	2.乘方
		var num2=Math.pow(3,2);//3的2次方
		alert(num2);//结果9

## 16进制和8进制	
	十进制：逢十进一。（有效数字：0,1,2,3,4,5,6,7,8,9）
	
	八进制：逢八进一。（有效数字：0,1,2,3,4,5,6,7）
		八进制：92；//这是不对的
	
	十六进制：逢十六进一（有效数字：0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F）
	
	二进制：逢二进一（有效数字：0,1）；
	
	二、进制转换
	2.1 其它进制转十进制。
	
	1).十进制转十进制；
		十进制328；
		328 = 3*100+2*10+8 = 3*10^2+2*10^1+8*10^0(m*进制的(n-1)次方）=328
	
	2）.八进制转十进制
		八进制的326
		326 = 3*8^2+2*8^1+6*8^0 = 192 + 16 + 6 = 214;
	
	3）.十六进制转十进制
		D3F = 13*16^2 + 3*16^1+15*16^0  = 13*256(3328) + 48 + 15 = 3391;
	
	4).二进制转十进制
		1010 = 1*2^3+ 0*2^2+1*2^1+0*2^0 = 10;
		1010 = 8+2 = 10；
		1011 = 8+2+1 = 11;
		1111 = 8+4+2+1 = 15; 
	
	2.2 十进制转其它进制。
	短除法
	1).十进制转十进制；
		十进制328；
	
	10  |328
		-----  8
	  10 |32
	     ----  2
	   10 |3  
	      --- 3
	       0
	
	2).十进制转二进制； 十进制的数字除以2 ，商继续除以2，直到商为0 ，把每一步的余数倒着取出来就是结果。
		11 = 1011；
		
		  2 | 11
			----- 1
			2 |5
			 ----- 1
			 2 |2
			  ----  0
			  2 |1
				---  1
				0	   	   


	三.进制表示
		var n1 = 56;//默认是十进制
		var n2 = 056;//表示八进制的56
		alert(n2);//显示时会直接转为十进制 46
		var n3 = 0x56;//表示十六进制的56
		alert(n3);//显示时会直接转为十进制 86
	
	四.求俩个数之和写法：
	function testf() {
			//1、获取用户输入的内容
			var num1 = document.getElementById("num1").value;
			var num2 = document.getElementById("num2").value;
			//2、加法
			var num3 = Number(num1)+Number(num2);	
			//3、把交换后的结果显示在文本框里
			document.getElementById("num3").value = num3;
		}

## 转义字符

	一、转义字符
		在任何计算机语言中，
	1、总有一些字符代表特殊的意义（如：双引号代表字符串的开始和结尾），如果我们想用字符本身，那就得用转义字符。
	2、还有些字符，没法直接输出，也得用转义字符
	
	二、js中转义字符的表示，以反斜杠（捺）开头，后面紧跟字符本身，
		如： \" 表示双引号  \' 表示单引号； \\ 表示 \
		如： \n 表示换行
	
	function testf() {
			alert("hello\"");
			alert("hello\n world");
		}

## 选择语句	

	 单分支语句：
	只有一条分支的条件语句。没有else语句块的if语句就是单分支。
	if(num1>0){
	alert(“大于零”);
	}
	  双分支语句：
	有两条分支的条件语句是双分支语句。
	  多分支语句：
	两条以上的分支语句叫多分支语句。
	  嵌套分支语句：
	分支语句中套分支语句，可以用来实现多分支。
	
	1.if的单分支
		if(条件){ //条件一般是关系表达式或者逻辑表达式
			语句
		}
	
	2.if的双分支
	if(条件){
		语句一
	}else{
		语句二
	}
	
	3.if的多分支
	if(条件一){
		语句一
	}else if(条件二){
		语句二
	}else{
		语句三
	}
	
	4.if的嵌套？
	if(条件一){
		if(条件一一){
			语句一一
		}else{
			语句一二
		}
	}else if(条件二){	
		if(条件二一){
			语句二一
		}else{
			语句二二
		}
	}else{
		语句三
	}
### 举例“闰年”

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		
	</head>
	<body>
		亲，请输入一个年：<input id="yearId" type="text" />
		<input type="button" value="是闰年还是平年" onclick="testf()" />
		<input id="resultId" type="text" />
	</body>
</html>
<script type="text/javascript">
//生活中：四年一闰，百年不闰，四百年一闰

function testf() {
	//1、获取文本框的内容
	var year = Number(document.getElementById("yearId").value);
	
	//2、判断
	var str;
	if((year%4==0 && year%100!=0)||(year%400==0)){
		str=year+"是闰年";
	}else{
		str=year+"是平年";
	}

	//3、显示
	document.getElementById("resultId").value = str;
}

</script>
```

### 示列“三分支”

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		
	</head>
	<body>
		身高：<input id="heightId" type="text" />厘米<br/>
		体重：<input id="weightId" type="text" />千克<br/>
		<input type="button" value="计算你的体型" onclick="testf()" />
		<input id="resultId" type="text" />
	</body>
</html>
<script type="text/javascript">
//

function testf() {
	//1、获取文本框的内容
	var height = Number(document.getElementById("heightId").value);
	var weight = Number(document.getElementById("weightId").value);
	
	//2、判断
	var str;
	var standardWeight = height-105;
	if(weight<standardWeight-5){
		str="亲，您多吃点，要飘起来了！";
	}else if(weight>standardWeight+5){
		str="亲，您少吃点，地球有意见！";
	}else{
		str="亲，您是魔鬼身材，好崇拜噢！"
	}
	
	//3、显示
	document.getElementById("resultId").value = str;
}

</script>
```

### 示列“嵌套”

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		
	</head>
	<body>
		亲，请输入一个x：<input id="numId" type="text" />
		<input type="button" value="计算y" onclick="testf()" />
		<input id="resultId" type="text" />
	</body>
</html>
<script type="text/javascript">
    
function testf() {
	//1、获取文本框的内容
	var x = Number(document.getElementById("numId").value);
	
	//2、判断
	var y;
	
	if(x<1){
		y = x;
	}else{
		if(x<10){
			y = 2*x+1;
		}else{
			y = 5*x+17;
		}
	}	
	//3、显示
	document.getElementById("resultId").value = y;
}

</script>
```

## 多分支语句switch 

	语法：
		switch(表达式){
		case 表达式1:分支语句一;break;
		case 表达式2:分支语句二;break;
		case 表达式3:分支语句三;break;
		…
		case 表达式n:分支语句n;break;
		default:默认分支语句;break;
	}
	
		switch表达式的值和case表达式的值进行比较，两值相等就执行case对应的分支语句。分支语句可有有任
	意多个，如果没有任何case表达式的值与switch表达式值相等就执行default的默认分支语句。
	因为执行完分支语句后不会自动退出switch语句，会继续执行后续的分支语句，这叫做switch的穿透，为
	避免穿透，需要在每条分支语句后添加break，跳出switch语句。

### 示列“成绩”

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		
	</head>
	<body>
		亲，请输入您的成绩：<input id="scoreId" type="text" />
		<input type="button" value="计算等级" onclick="testf()" />
		<input id="resultId" type="text" />
	</body>
</html>
<script type="text/javascript">

switch(表达式){
	case 表达式1:语句一;break;
	case 表达式2:语句二;
	case 表达式3:语句三;break;
	……
	case 表达式n:语句n;break;
	default:默认语句
}

break:结束switch结构
case穿透：如果某个分支没有break，那就会出现case穿透。

function testf() {
	//1、获取文本框的内容
	var score = Number(document.getElementById("scoreId").value);
	
	//2、判断
	var level;
	if(score>=85 && score<=100){
		level = "A";
	}else if(score>=70 && score<85){
		level = "B";
	}else if(score>=60 && score<70){
		level = "C";
	}else if(score>=0 && score<60){
		level = "D";
	}else{
		level = "亲，您胡输入呢";
	}
	
	//3、显示
	document.getElementById("resultId").value = level;
}

</script>
```

### 示列"星期"

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		
	</head>
	<body>
		亲，请输入0-7之间的数字：<input id="numId" type="text" />
		<input type="button" value="显示汉字的星期" onclick="testf()" />
		<input id="resultId" type="text" />
	</body>
</html>
<script type="text/javascript">

function testf() {
	//1、获取文本框的内容
	var num = Number(document.getElementById("numId").value);
	
	//2、判断
	var str;

	switch(num){
		case 0:str="星期天";break;
		case 1:str="星期一";break;
		case 2:str="星期二";break;
		case 3:str="星期三";break;
		case 4:str="星期四";break;
		case 5:str="星期五";break;
		case 6:str="星期六";break;
		default:str="亲，您的输入有误";break;
	}
	
	//3、显示
	document.getElementById("resultId").value = str;
}

</script>
```

### while与do while的区别

	while和dowhile的区别：
		在于执行顺序。
	while：
		先判断循环条件，再执行循环体里的代码
	do while：
		先执行循环体里的代码，然后再判断。

## 三元运算符

	一元(单目)运算符：运算符需要一个操作数 ++，  --， ！
	二元(双目)运算符：运算符需要二个操作数 +，-，< , &&, ||
	三元(三目)运算符：运算符需要三个操作数 ? :
	
	格式：
		表达式一?表达式二:表达式三
	意思：
		当表达式一成立，那么就执行表达二，否则执行表达式三。

### 示列

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		
	</head>
	<body>
		数1：<input id="numId1" type="text" />
		数2：<input id="numId2" type="text" />
		<input type="button" value="谁大" onclick="testf()" />
		<input id="resultId" type="text" />
	</body>
</html>
<script type="text/javascript">

function testf() {
	//1、获取文本框的内容
	var num1 = Number(document.getElementById("numId1").value);
	var num2 = Number(document.getElementById("numId2").value);
	
	//2、判断
	var max;
	max = num1>num2?num1:num2;

	//3、显示
	document.getElementById("resultId").value = max;
}

</script>

```


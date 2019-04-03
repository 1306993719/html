# js 循环语句

## 循环：

	就是重复做一件事情，在程序中，就是循环执行一段代码
	一个循环包含：
		循环条件，循环体，循环变量（控制循环的变量）
	三种循环结构
	循环就是重复执行一段代码，是一种最能发挥计算机优势的程序结构。
	循环结构的代码由循环体、循环变量、和循环条件组成。当循环变量满足循环条件时会重复执行循环体内的代码，直到
	循环变量不满足循环条件时就终止循环，接着执行循环结构后的代码。
	
	循环的要点：
		1，循环变量要先初始化。
		2，每次循环前判断表达式，表达式成立后执行循环体语句。
		3，循环体中，应有结束循环的条件(有个代码朝着循环条件
			不满足的方向靠近)，否则会造成死循环。
		4，当不确定循环多少次时可用死循环。
		5，循环体中可以写若干句合法的javaScript代码，包括if，
			也可以再套个循环语句。
### while示列"1-100之和"

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

function testf(){
	//求1-100之和
	var sum = 0;
	var add = 1;
	while(add<=100){ //add是循环变量；add<=100是循环条件
		//是循环体。
		sum = sum+add;
		add++;
	}
	alert("sum="+sum);
	alert("add="+add);//101
}
</script>
```

### while示列"100内偶数之和"

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

// while(表达式){
// 	语句
// }

function testf(){
	//求1-100的偶数之和
	var sum = 0;
	var add = 1;
	while(add<=100){ 
		if(add%2==0){
			sum = sum+add;
		}
		add++;
	}

	alert("sum="+sum);
	alert("add="+add);//102
}
</script>
```

## for 循环

	for(表达式1;表达式2;表达式3){
		语句
	}
	
	for(循环变量赋初值;循环条件;循环变量（步长）){
		语句
	}
	
	for循环的特点是：
				把控制循环的执行次数放在了一起。
				把循环的控制和循环体分开
				显得结构清晰。

### 示列"奇偶数之和"

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

function testf(){
	var sum=0;
	//偶数之和：
	// for(var add=2;add<=100;add+=2){
	// 	sum = sum+add;
	// }
	
	for(var add=1;add<=100;add++){
		if(add%2==0){
			sum = sum+add;
		}	
	}

	//奇数之和
	// for(var add=1;add<=100;add+=2){
	// 	sum = sum+add;
	// }

	// for(var add=1;add<=100;add++){
	// 	if(add%2!=0){
	// 		sum = sum+add;
	// 	}	
	// }

	document.write(sum);
}
</script>
```

### 示列"100内n的倍数之和"

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

function testf(){
	var sum=0;
	for(var add=1;add<=100;add++){
		if(add%7==0){
			sum = sum+add;
		}	
	}
	document.write(sum);
}
</script>
```

### continue （继续）
	continue: 
		在循环体中，如果碰到了continue;语句，那么就结束本次循环，继续下次循环.

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></titl
	</head>
	<body>
		<input type="button" value="  测试  " onclick ="testf()" />
	</body>
</html>
<script type="text/javascript">
    
function testf(){
	for(var add=1;add<=10;add++){
		console.log(1);//把变量输出在控制台（console）
		continue;
		console.log(2);//把变量输出在控制台（console）
	}
}
</script>
```

### break(结束循环)
	break:
		也可以放在循环里，跳出循环（终止循环）。

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

function testf(){
	for(var add=1;add<=10;add++){
		console.log(1);
		break;
		console.log(2);
	}
	console.log(3);
}
</script>
```

### 死循环
	死循环：
		循环条件永远满足
		while(true){
		}
		do{
		}while(true);
		for(;;){
		}
## 循环的嵌套 

	1，一个循环内包含完整的另一个循环语句。
	2，被包含的循环语句叫内循环，包含别的循环的循环语句叫外循环。
	3，外循环每执行一次循环，内循环都会完全执行所有循环次数。,
	4，循环嵌套的总执行次数是外循环次数乘以内循环次数。
	
	注：
		可使用浏览器的调试功能一步步查看循环嵌套的执行

### 示列"打印矩形"

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<input type="button" value="测试" onclick ="testf()" />
	</body>
</html>
<script type="text/javascript">
/*
☆☆☆☆☆
☆☆☆☆☆
☆☆☆☆☆
*/
function testf(){

	for(var i=0;i<3;i++){
		// document.write("☆☆☆☆☆<br/>");
		for(var j=0;j<5;j++){
			document.write("☆");
		}
		document.write("<br/>");
	}

}
</script>
```

### 示列"九九乘法表"

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

function testf(){

	for(var i=1;i<=9;i++){
		for(var j=1;j<=i;j++){
			document.write(j+"*"+i+"="+(i*j)+"&nbsp;&nbsp;");
		}
		document.write("<br/>");
	}	
}
</script>
```


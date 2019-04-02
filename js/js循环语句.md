# js 循环语句

## 循环：

	就是重复做一件事情，在程序中，就是循环执行一段代码
	一个循环包含：
		循环条件，循环体，循环变量（控制循环的变量）
	三种循环结构
	循环就是重复执行一段代码，是一种最能发挥计算机优势的程序结构。
	循环结构的代码由循环体、循环变量、和循环条件组成。当循环变量满足循环条件时会重复执行循环体内的代码，直到
	循环变量不满足循环条件时就终止循环，接着执行循环结构后的代码。
### 示列"1-100之和"

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

### 示列"100内偶数之和"

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


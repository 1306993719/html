# 数组

## 数组概念及定义
		一个变量只能存储一个数据，如果我们有一组数据，比如1到100一百个数字，定义100个变量来
	存储就太痛苦了，这时候我们就需要数组来存储这样的数据。
	
	定义数组
	1、构造函数的方式
		var arr1 = new Array(8);//定义了一个数组，可以存放八个数据（元素），这八个数据没有值。
		var arr2 = new Array(2,3,4);//定义了一个数组，里面有3个数据（元素），分别是2,3,4
	
	2、常量（字面量）的方式
		var arr3=[12,23,43];////定义了一个数组，里面有3个数据（元素），分别是12,23,43

## 数组的几个概念
	Length（长度）:
		数组中包含的元素个数。
		
	例：
		var arr1=new Array(7);
		alert(arr1.length); //输出结果为7
		
	下标（索引）:
		数组中元素的序号，从0开始，下标最大取值是“长度-1”；下标可以是变量或表达式。我们通
		过索引来访问数组中任意元素。
		
	例：
		var arr1=[1,2,3,4,5];
		alert(arr1[0]); //输出结果是1，下标0代表第一个元素
		alert(arr1[arr1.length-1]); //输出结果是5，下标length-1代表最后一个元素
		arr1[2]=7; //通过下标修改了第三个元素的值
		alert(arr1[2]); //输出结果是7，

## 数组的常用方法
	push() 方法向数组的末尾添加一个或多个元素，并返回新的长度。
		var arr1=[1,2,3];
		var len=arr1.push(7); //向数组末尾添加元素,并返回数组的新长度
		alert(len); //输出4
		
	pop() 方法删除并返回数组的最后一个元素。
		x=arr1.pop(); //删除最后一个元素并返回被删除的元素
		alert(x); //输出7
		
	unshift()向数组的开头添加一个或多个元素，并返回新的长度。
		x=arr1.unshift(8,9); //向数组开头添加了两个元素，并返回新长度
		alert(x); //输出5
		
	shift() 方法把数组的第一个元素从其中删除，并返回第一个元素的值。
		x=arr1.shift(); //删除第一个元素并返回被删除的元素
		alert(x); //输出8
	
	concat() 连接两个或更多的数组，并返回结果。 
	join() 把数组的所有元素放入一个字符串。元素通过指定的分隔符进行分隔。 
	reverse() 颠倒数组中元素的顺序。 
	slice() 从某个已有的数组返回选定的元素 
	sort() 对数组的元素进行排序 
	splice() 删除元素，并向数组添加新元素。 
	toSource() 返回该对象的源代码。 
	toString() 把数组转换为字符串，并返回结果。 
	toLocaleString() 把数组转换为本地数组，并返回结果。  
	valueOf() 返回数组对象的原始值 

## 数组的遍历
		通常操作数组时，每个元素都要操作一遍，这个时候我们会用循环来访问每一个元素，循环
	访问数组的每一个元素就叫做数组的遍历。
	
	for循环方式：
		var arr1=[1,2,3,4,5,6];
		for(var i=0;i<arr1.length;i++){
			console.log(arr1[i]);
		}
		
	for in 方式：
		var arr1=[1,2,3,4,5,6];
		for(var i in arr1){
			console.log(arr1[i]);
		} 

## 二维数组
		数组内的每一个元素也是一个数组
	
	二维数组就是嵌套数组，数组的元素也是个数组
		var arr = [[1,2,3],[5,6],8];
		console.log(arr.length);//3
		console.log(arr[0][0])//1;
		console.log(arr[0][1])//2;
		console.log(arr[2])//8;

### 示列"二维数组的遍历"

```html
doctype html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<input type="button"  value=" 测试 " onclick="testf()" >	
</body>
</html>
<script type="text/javascript">
function testf() {
	
	var arr = [[1,2,3],[5,6],[78,12]];

	for(var i=0;i<arr.length;i++){
		for(var j=0;j<arr[i].length;j++){
			console.log(arr[i][j]);
		}
		console.log("-----------");
	}
}
</script>
```

## 数组的排序-冒泡
		数组的数据如果是无序的，经常需要按大小个排序。排序算法有很多，我们介绍最常见的两个。
	冒泡排序和选择排序。
	
	冒泡排序算法的运作如下：
		从第一个元素开始比较后一个元素，只要前一个元素大于后一个元素就交换两元素位置。比完后最大的
	元素应该就移动到数组最后的位置。
	针对所有的元素重复以上的步骤，除了最前一个。
	持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。

### 示列"冒泡排序"

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<input type="button" value="  排序 " onclick ="testf()" />			
	</body>
</html>
<script type="text/javascript">
//冒泡排序：相邻两个数进行比较，如果前一个数比后一个数大，那么就交换。
//举例说明：
// var arr=[8,7,9,4,2,1];
/*

第一轮:i=0;
比较5次，内层循环是5次
j =  0            1              2

 	 8            7               7          7        7        7
	 7            8               8          8        8        8
	 9            9               9          4        4        4
	 4            4               4          9        2        2
	 2            2               2          2        9        1
	 1            1               1          1        1        9
arr[0]>arr[1]  arr[1]>arr[2]  arr[2]>arr[3] 
arr[j]>arr[j+1]

第二轮:i=1;    
比较4次，内层循环是4次
j =   0     1

	  7         7              7     7      7
	  8         8              4     4      4
	  4         4              8     2      2
	  2         2              2     8      1
	  1         1              1     1      8
	  9         9              9     9      9
arr[0]>arr[1]  arr[1]>arr[2]  arr[2]>arr[3] 
arr[j]>arr[j+1]  
  
第三轮:i=2;  
比较3次，内层循环是3次
j =  0 
	  7     4     4      4
      4     7     2      2
      2     2     7      1
      1     1     1      7
      8     8     8      8
      9     9     9      9
	
第四轮	
	  4      2     2
	  2      4     1
      1      1     4
      7      7     7
      8      8     8
	  9      9     9

第五轮	   
	  2   1
      1   2
      4   4
      7   7
	  8   8
	  9   9
*/
    
function testf() {
	var arr= [8,7,9,4,2,1];

	//2、冒泡的逻辑
	for(var i=0;i<arr.length-1;i++){
		for(var j=0;j<arr.length-1-i;j++){
			//比较
			if(arr[j]>arr[j+1]){
				var temp = arr[j];
				arr[j] = arr[j+1];
				arr[j+1] = temp;
			}
		}
	}
	//3、输出数组所有的元素
	for(var i=0;i<arr.length;i++){
		console.log(arr[i]);
	}

}
</script>

```

## 数组的排序-选择
		从所有元素中先找到最小的，然后放到第一个位置。之后再看剩余元素中最小的，放到第二个位置……
	以此类推，就可以完成整个的排序工作了。

### 示列"选择法排序"

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<input type="button" value="  排序 " onclick ="testf()" />			
	</body>
</html>
<script type="text/javascript">
//选择法排序：从所有元素中先找到最小的，然后放到第一个位置。之后再看剩余元素中最小的，放到第二个位置……以此类推，就可以完成整个的排序工作了

// 8,7,9,4,2,1

/* i=0;

  找最小数(从arr[0]到最后一个数)，然后交换（最小数和arr[0]）
  
  1,7,9,4,2,8

  i=1	
  找最小数(从arr[1]到最后一个数)，然后交换（最小数和arr[1]）
  1,2,9,4,7,8

  i=2	
  找最小数(从arr[2]到最后一个数)，然后交换（最小数和arr[2]）
  1,2,4,9,7,8
  1,2,4,7,9,8
  1,2,4,7,8,9
*/

function testf() {
	var arr= [8,7,9,4,1,2];

	//2、选择法的逻辑
	for(var i=0;i<arr.length-1;i++){
		//1、找最小数
		//方法一：
		// var min = arr[i];//1
		// var minIndex = i;//minIndex记录最小数的下标
		// for(var j=i+1;j<arr.length;j++){
		// 	if(arr[j]<min){
		// 		min = arr[j];
		// 		minIndex = j;
		// 	}
		// }

		//方法二：
		var minIndex = i;//minIndex记录最小数的下标
		for(var j=i+1;j<arr.length;j++){
			if(arr[j]<arr[minIndex]){
				minIndex = j;
			}
		}

		//2、交换
		var temp = arr[minIndex];
		arr[minIndex] = arr[i];
		arr[i] = temp;	
	}

	//3、输出数组所有的元素
	for(var i=0;i<arr.length;i++){
		console.log(arr[i]);
	}
}
</script>
```





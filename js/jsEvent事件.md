## 事件的概念
	什么是事件：
		事件是发生并得到处理的操作，即：事情来了，然后处理。
		
	事件触发：
		当用户点击按钮时，我们就说，触发了按钮的onclick事件。
		
	事件处理程序：
		也就是响应（处理）某个事件的函数。
		事件与事件处理程序建立对应关系的过程我们称为给事件绑定函数，或给事件注册函数。现在常用的绑定方式有DOM0级，DOM2级和IE特殊方式。

## DOM0
	1，使用HTML属性指定方式，如果要调用函数，这个函数在JS中要处于全局作用域。
	
	2，DOM对象事件属性绑定（匿名函数方式）
	DOM对象事件属性绑定的方式的优点
	解耦（降低了耦合度），即：把HTML代码和JavaScript代码的耦合度降低了。
	耦合度：联系的程度
	
	1，使用HTML属性指定方式，如果要调用函数，这个函数在JS中要处于全局作用域。
		<input type="button" id = "button1" value="按钮" onclick="queren(this)">
			function queren(data) {
				alert(data.value);
			}
		
	2，匿名函数方式
		var btn1=document.getElementById(" button1 ");
			btn1.onclick = function () {
				alert(this.value);
			}
		btn1.onclick =""; //可取消两种方式事件处理函数的绑定。

## 常见DOM0事件
	onchange 域的内容被改变（下拉列表选择改变）。
	onclick 当用户点击某个对象时调用的事件。
	ondblclick 当用户双击某个对象时调用的事件。
	onfocus 元素获得焦点。
	onblur 元素失去焦点。
	onkeydown 键盘上某个按键被按下。
	onkeyup 键盘上某个按键被松开。
	onkeypress 键盘上某个按键被按下并松开。
	onload 一张页面或一幅图像完成加载。
	onmousedown 鼠标按钮被按下。
	onmouseup 鼠标按键被松开。
	onmouseover 鼠标移到某元素之上。
	onmouseout 鼠标从某元素移开。
	onmousemove 鼠标被移动。
	onreset 重置按钮被点击， 引发Form重置事件。
	onresize 窗口（body）或框架被重新调整大小。
	onsubmit 确认(提交)按钮被点击， 引发Form提交事件。
	onunload （body）用户退出（刷新）页面。

## DOM2级
	DOM0级很浓的绑定味道，DOM2真正体会注册的概念。
	addEventListener和removeEventListener（事件监听器）
	
	这两个方法接受3个参数，要处理的事件名，处理函数，和一个布尔值。这个布尔值代表在捕获节点调用事件处理程序(true)还是在冒泡过程中调用(false)。
		
	function dianjia(){ //事件处理程序
		alert('this is a div');
	}	
	
	var div1=document.getElementById("a");
		div1.addEventListener("click",dianjia,false); //为click事件注册事件处理程序
		div1.addEventListener("click",function(){alert("注册的匿名事件处理程序");},false);
		//匿名方式为click事件注册第二个事件处理程序
	
	div1.removeEventListener(“click”, dianjia, false);
		DOM2级的事件解绑（要求，绑定时的函数是有名字的）
		解绑时，不能解绑匿名的事件处理函数

### DOM0级和DOM2级的区别
	DOM0级，在同类型的事件里只能绑定一个事件处理函数
	DOM2级，在同类型的事件里只能绑定多个事件处理函数

## IE事件

	IE8及其以前的版本不支持DOM2级注册方式，自己提供了attachEvent和detachEvent来实现相似功能。注销时同样需要传入相同的参数，匿名函数无法注销。
	
	function dianjic(){
		//event.stopPropagation();
		alert(this === window);
		//alert('this is c div');
	}
	div1.attachEvent(“onclick",dianjia);
	div1.attachEvent(“onclick", function(){alert("注册的匿名事件处理程序");});
	div1.detachEvent(“onclick", dianjia);

## 几种事件绑定方式对比 

|                |          DOM0           |                DOM2                 |                 IE                  |
| :------------: | :---------------------: | :---------------------------------: | :---------------------------------: |
|     事件名     |    事件名以"on"开 头    |          事件名前没有"on"           |           事件名以“on”头            |
|      冒泡      |          支持           |       支持，最后属性设为false       |                支持                 |
|      捕获      |         不支持          |       支持，最后属性设为true        |               不支持                |
|    阻止冒泡    | event.stopPropagation() |       event.stopPropagation()       |       event.cancelBubble=true       |
| 多处理程序注册 |         不支持          |                支持                 |    支持，执行顺序与注册顺序 相反    |
|  删除事件绑定  |     设置为空或null      | 用处理程序名删除，匿名绑 定不能删除 | 用处理程序名删除，匿名绑 定不能删除 |
|     兼容性     |         全兼容          |                非IE                 |                 IE                  |

## event对象
	event对象：
	event对象只在事件发生（如：点击事件）的过程中才有效。如：当点击按钮时，就会自动产生
	event对象。event对象是自带的对象，是固定写法。
	
	在W3C标准中，直接在函数中声明该参数即可
	btn.onclick = function(event) { //event在调用和函数定义时，都写上也是考虑兼容问题
	};
	
	兼容性写法，支持老版本的IE
	var evt = event ? event : window.event;或者 var evt = event || window.event;

|     属性/方法     |   类型   | 读写 |                    说明                    |
| :---------------: | :------: | :--: | :----------------------------------------: |
|      bubbles      | Boolean  | 只读 |                事件是否冒泡                |
|    cancelable     | Boolean  | 只读 |         是否可以取消事件的默认行为         |
|   currentTarget   | Element  | 只读 | 当前正在处理事件的那个元素(IE是srcElement) |
|      detail       | Integer  | 只读 |            与事件相关的细节信息            |
|    eventPhase     | Integer  | 只读 |       阶段：1捕获，2处于目标，3冒泡        |
| preventDefault()  | Function | 只读 |     取消事件的默认行为（例： keydown）     |
| stopPropagation() | Function | 只读 |           取消进一步的捕获或冒泡           |
|      target       | Element  | 只读 |                 事件的目标                 |
|       type        |  String  | 只读 |                 事件的类型                 |

## event对象的键盘事件相关属性
	altKey 返回当事件被触发时，"ALT" 是否被按下。
	shiftKey 返回当事件被触发时，"SHIFT" 键是否被按下。
	ctrlKey 返回当事件被触发时，"CTRL" 键是否被按
	keyCode（火狐用which）获取按键的键码
	
	event的兼容写法:
		var evn=event||window.event; //取得event对象，兼容IE的写法
		var ele=evn.currentTarget||evn.srcElement; //当前事件元素,兼容IE写法
		var keycode = evn.which || evn.keyCode;	//兼容火狐的写法
		
	在keydown和keyup事件里，属性keyCode保存着键盘的虚拟码，
	每个键的虚拟码是唯一的。一个数字对应一个键。
	
	在keypress事件里，属性keyCode保存着每个键对应ASCII码，
	这些键跟显示有关。
## event对象的鼠标事件相关属性
	button 鼠标按键事件中按了哪个鼠标键，0左1中2右，低版本IE：1左2右3左右4滚轮5左加滚轮6右加滚轮7三个同时
	clientX 基于浏览器可视区域的左上角的鼠标x坐标。
	clientY 基于浏览器可视区域的左上角的鼠标y坐标。 。
	screenX 基于显示器左上角的鼠标x坐标。
	screenY 基于显示器左上角的鼠标y坐标。
	pageX 基于网页左上角的鼠标x坐标。
	pageY 基于网页左上角的鼠标y坐标。
	offsetX 基于事件元素(事件源)左上角的鼠标 x 坐标。
	offsetY 基于事件元素(事件源)左上角的鼠标 y 坐标。

## 阻止浏览器默认行为
	w3c使用 event.preventDefault()，IE则是使用event.returnValue = false;
		
	注：
		事件处理函数直接返回false也行的。
		
	按键事件结束后字符应该输入到文本框，超链接跳转，表单提交，右键菜单的弹出等。
	
	if (event.preventDefault) {
		event.preventDefault();
	} else {
		event.returnValue = false;
	} 

## 鼠标拖拽
	1，给目标元素添加onmousedown事件；document添加onmousemove事件和onmouseup事件。
	
	2，目标元素的onmousedown事件，计算鼠标和目标元素的坐标差。
		鼠标和元素的横坐标差 x = 鼠标的clientX –目标元素的left
		鼠标和元素的纵坐标差 y = 鼠标的clientY–目标元素的top
		同时记录鼠标键被按下。
		
	3，document的onmousemove事件，如果鼠标是按下状态，让目标元素跟随鼠标。
		目标元素的left = 鼠标的clientX + 鼠标和元素的横坐标差 x。
		目标元素的top = 鼠标的clientY + 鼠标和元素的纵坐标差 y。
		
	4，document的onmouseup事件，记录鼠标键被放开。
		拖拽事实上是给跟随鼠标增加了一个开关，鼠标按下打开开关，鼠标弹起关闭开关。
		
	注： 
		onmousemove和onmouseup绑定到document上代替目标元素来做事情，这就是事件委托。

### onmouseover和onmouseenter的区别
	onmouseover和onmouseout，会受冒泡的影响，而且进入子元素，会触发父元素onmouseout事件

	onmouseenter和onmouseleave，不会受冒泡的影响，而且进入子元素，不会触发父元素onmouseleave事件，只有离开父元素的区域，才触发父元素onmouseleave事件。

## 事件冒泡和事件捕获的区别：

	1、从事件流向的角度说：
	事件冒泡：
		当触发了某个元素的某类型(如：onclick)的事件后，该元素的父元素的同类型（如：onclick）的事件也会被触发，依次类推最终会触发到最根的元素网上会有这样的说法：从具体的元素（事件源）到不具体（不确定的元素）。
	
	事件捕获：
		与事件冒泡相反，从根元素朝事件源进行触发的。
		网上会有这样的说法：从不具体的元素到确定的元素（事件源）。
		
	2、从支持的角度：
	DOM2级既支持冒泡又支持捕获
	DOM0级只支持冒泡
	IE只支持冒泡

## 请问DOM事件流(流向)
	DOM事件流分为三个阶段：
	1、第一个阶段是捕获阶段
	2、第二个阶段是事件源
	3、第三个阶段是冒泡阶段

## target和currentTarget的区别
	target:是真正的事件源，即触发事件的元素
	currentTarget:事件流流到哪个元素，就是哪个元素。

## 事件代理
	事件代理: 
		把本该属于某个元素的事件委托给他的父级元素。
		事件代理是利用冒泡（子元素的事件会冒泡到父元素），
		把本该属于li的事件委托给他的父元素ul。
		
	优点：
		1、绑定的事件少了
		2、后添加的子元素，依然事件有效

### 示列"事件代理"

```html
<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>作业5</title>
</head>
<body>
	<ul id="ulbox">
		<li>第1个li</li>
		<li>第2个li</li>
		<li>第3个li</li>
	</ul>
	<input id="btn01" type="button" value="添加li" >
</body>
</html>
<script type="text/javascript">
function $(id){
	return document.getElementById(id);
}

var index = 3;
window.onload = function(){
	$("btn01").onclick = function(){
		var liDom = document.createElement('li');
		index++;
		liDom.innerHTML = '第'+index+'个li';
		$("ulbox").appendChild(liDom);
	}

	//事件代理: 把本该属于某个元素的事件委托给他的父级元素。
	// 事件代理是利用冒泡（子元素的事件会冒泡到父元素），
	//把 本该属于li的事件委托给他的父元素ul。
	//优点：
	//1、绑定的事件少了
	//2、后添加的子元素，依然事件有效

	$("ulbox").onclick = function(event){
		var evt = event || window.event;
		// alert(this.innerHTML);
		if(evt.target.tagName.toLowerCase()=="li"){
			alert(evt.target.innerHTML);
		}
	}
}

</script>
```


###总结
**`网址`**
>域名解析 --DNS --服务器的IP地址  ：端口号去查找你的项目在哪个端口下
>协议
>>HTTP:超文本传输协议    80
>>HTTPS（安全嵌套层）：比较超文本传输协议更安全的协议 443
>>FTP：给服务器上传文件
>域名
>>一级域名  www.qq.com
>>二级域名  qq.news.com

>端口号 80 443  


**`AJAX`**
>1.定义  Async JavaScript and XML
>2.作用：局部刷新
>3.AJAX  5步
````javascript
//兼容
var xhr = new XMLHttpRequest();

/*
* responseText: ""  获取服务器响应主体内容（JSON）
  responseType: ""  服务器返回内容类型
  responseURL: ""  响应的url地址
  responseXML: null    获取服务器响应主体内容（XML）
  status:   网略状态吗
  statusText: ""   网络状态码描述
* */


/*
* AJAX的处理进度
* DONE: 4  响应主体内容已经返回
  HEADERS_RECEIVED: 2    已经开始接受服务器响应头信息
  LOADING: 3        正在加载服务器响应主体内容
  OPENED: 1   已经发送AJAX请求
  UNSENT: 0  还没有发送请求   实例已经创建
* */


/*
* 网络状态码
* 200:请求成功，但是获取的响应主体内容不一定是我们想要的
* 301:永久重定向  360buy  
* 302:零时重定向零时转移  （http-->https负载均衡
* 304:从缓存中获取
* 404：找不到地址
* 400：请求参数错误
* 500：未知错误
* 503：服务器超出负荷
* */
xhr.open("请求方式","请求路径","同步异步","[username],[userpass]");
xhr.onreadystatechange = function() {
   if (/^(2|3)\d{2}$/.test(xhr.status)){
       if (xhr.readyState ==2){
           
       } 
       
       if (xhr.readyState ==4){
           
       } 
   } 
}


//传递的参数是请求主体内容
xhr.send(null);


/*
get:给服务器传递参数？传参
delete:删除服务器内容
head
options:axios(基于promise封装AJAX库)，发送请求的时候先发送了一次options请求去探测请求是否成功，成功才会做下来的事情

post/put（给服务上传内容）:请求中
* */
````

**`promise`**
>异步管控，但是也可以管理同步（没意义）
>解决回调地狱
````
//我们第一次请求数据服务器返回的响应主体内容做为第二请求的参数
ajax({
    success:function(data){
        ajax({
            data:data,
            success:function(data){
                ajax({
                })
            }
        });
    }
});

//把 嵌套的方式改为串行的方式
//excutor：执行器  并且是一个函数，但是这个函数创建实例的同事执行执行了  
//excutor：两个参数  reslove  reject 
var pro =  new Promise(function(reslove,reject){}){
      ajax({
          success:function(data){
               reslove(data);
      });      
}

pro.then(function(result){
       ajax({
           success:function(result){
              
           }
       });
});

````

**`跨域`**
>JSONP
````javascript
// <script src="http://127.0.0.1:8000/index.html?call=fn"></script>
//call和服务器商量的名字

//在全局下定义个函数
function fn(data) {
  
}

// cors：服务器设置

  	// res.header("Access-Control-Allow-Origin", "*");
  	
  	//指定端口进行
  	//res.header("Access-Control-Allow-Origin", "http://127.0.0.1:8000");
  	
  	
  	
//webpack proxy （webScoket） （常用） 代理
//ngix反向代理*/  
````

**`闭包和原型`**
>作用域   函数执行形成一个私有作用域
>作用炼狱  作用域之间查找机制就形成作用链
>闭包：函数执行形成一个私有作用域外边不能进行访问和修改
>>防止全局污染  
>>把局部变量始终保存内存中(不销毁的)

>>堆栈内存释放
>栈内存是自动回收浏览器（辣鸡回收机制）
>>堆内存：手动释放  obj = null;

>>原型：
>>每一个函数或类都有一个prototype属性
>>我们可以在原型上增加公共方法

>>当前实例有私有的先找私有的没有私有再去找公有
````javascript
__proto__

//跳过当前原型在上一级原型上进行设置
Fn.prototype.__proto__.getX= function() {
  
}


fn.getX();//先看私有再看公有
fn.__proto__.getX();//直接看公有，不看私有


//原型上通过__proto__这种查找机制就形成了原型链
````

**`继承方式`**
````javascript
//批量扩展公有方法
function A() {
  this.name = "aa";
}

A.prototype = {
    constructor:A,
    getX:function() {
      
    },
    
    getY:function() {
      
    }    
};
//原型继承(将父类私有+公有--->子类公有)
//让子类的原型指向父类的实例   
//让当前的constructor属性指向自己

//call继承  私有-->私有
function B() {
  this.a = 100;
}

function C() {
    B.call(this);
}

var c = new C();

//混合继承  原型继承+call继承
//把父类私有加公有给子类私有和公有
````
**`设计模式`**
>单利模式
>>在真是项目中一般都是模块开发当前在同一个命名空间下的方法和属性与其他命名空间下是相互独立的
>>工厂模式  没有什么用上
>>构造函数模式
>>发布订阅（观察模式）
>>1.先自己创建一个计划表
>>2.可以对计划表的内容进行增加和修改
>>3.可以通知计划表中的内容一次触发



###jQUERY
````javascript
//1.入口函数
$(document).ready(function() {
});

$(function() {
  
});
//2.选择器
//基本选择器  $("")
//$("#id值")；
//$(".class值")；
//$("eleName")；

//层级选择器
//$("选择器1 选择器2")；
//$("选择器1 > 选择器2")；
//$("选择器,选择器2")；
//$("eleName.select")；

//过滤（伪类）
//$("选择器1：eq(索引)")；
//$("选择器1：odd(索引)")；
//$("选择器1：even(索引)")；

//表单
//$("input:checked)；
//$("input:selected)；
//$("input:disabled)；


//筛选选择器（都是方法）
//$("选择器").first()；
//$("选择器").last()；
//可以不传递参数  获取所有子元素   传递参数获取的实当前标签对应元素
//$("选择器").children("div")；
//可以传递参数，如果传递了获取的传递参数对应的所有相邻元素
//$("选择器").siblings("div")；
//$("选择器").prev("div")；
//$("选择器").prevAll("div")；
//$("选择器").next("div")；
//$("选择器").nextAll("div")；
//获取父集元素
//$("选择器").parent()；


//3.jq对象和js对象相互是不可以调用内部的方法的
//js对象和jq对象相互转化：
//js对象转jq对象  $(jsObj);

//get();是转为一个数组  get(0);第一个元素   
//jq对象转js对象  $("div").get();  --> 数组   $("div").get(0);-->第一个元素  $("div")[索引];

//4.样式
//css
//单个样式   css("样式名"，"样式值");
// $("div").css("color","red");
//多个个样式   css({属性名：属性值，属性名：属性值，属性名：属性值..});

//class
//addClass("类名");
//removeClass("类名");
//toggleClass("类名"); 切换 


//5.属性
//index();当前元素对应索引


//6.动画
//(1）三组基本动画
//显示/隐藏/切换
//传递参数：
//slow 200ms   normal:400ms  fast600ms
//直接ms数

//第一组不传递参数没有动画效果
//show();  hide(); toggle();
//滑入/滑出、切换
//slideDown  slideUp  slideToggle();
//淡入/淡出、切换
fadeIn/fadeOut/fadeToggle 
//(2)自动义动画
//{}:改变的样式    时间：毫秒   运动方式（swing/linear）  回调函数（动画完成要做到事情）
//参数可以省略
 //jqObj.animate({},时间，运动方式，回调函数);
 //我们可以自己手动的去结束动画（结束上一次执行的动画效果）
 //stop();
 
 
 //7.循环遍历
 //each
 //(1)给原型添加循环遍历
 //(2)给实例添加的循环遍历
 //(3)隐式迭代
 
 
 //8.关于节点的操作
 
//（1）.创建节点
//传递的参数是拼接好的html节点字符串
$("<li>你好</li>");

//（2）添加
//添加到末尾
//append        父亲.append(儿子);
//appnedTo         儿子.appendTo(父亲);

//添加到开头
//prepend       父亲.prepend(儿子);
//prependTo     儿子.prependTo(父亲);
//insertAfter   把所有匹配的元素插入到另一个、指定的元素元素集合的后面。
//insertBefore  把所有匹配的元素插入到另一个、指定的元素元素集合的前面。
//empty :清空内容
// $("#myUl").empty();
//remove：删除
//$("#myUl").remove();


//attr
//一个参数 获取
//二个参数  设置

//prop:表单元素
//一个参数 获取
//二个参数  设置

//克隆参数为false:不克隆事件，参数为true克隆事件
//clone();
//获取表单元素的值
//val()

//如果在API中看到（参数中有val）,不传递的情况下是获取，传递就是设置

//1.offset:距离可视窗口的偏移返回的是一个对象
//2.position:父亲距离已经定位元素的偏移
//scrollTop：滚动条距离上面偏移量
//$(window).scroll(function () {
//    console.log($(document).scrollTop());
//});
//scrollLeft：滚动条距离上面偏移量
//width/height
//console.log($("#box").width());
//console.log($("#box").height());
//传值可以改变div的值
//$("#box").width(800);
//innerWidth/innerHeight  ====>clientWidth/clientHeight  width+padding
//console.log($("#box").innerWidth(),$("#box").get(0).clientWidth);
//outerWidth/outerHeight =====>offsetWidth/offsetHeight  width + padding + border
//console.log($("#box").outerWidth(),$("#box").get(0).offsetWidth);

//获取一屏幕的宽度和高度
//var win = document.documentElement.clientWidth || document.body.clientWidth;
//var win1 = $(window).outerWidth();
//console.log(win,win1);

//$(window).on("resize",function () {
//    console.log($(window).outerWidth());
//}); 

//AJAX中的属性
//setRequestHeader//当前发送给服务器的格式
// xhr.setRequestHeader("name","RC");
//pplication/x-www-form-urlencoded
//设置请求的编码方式
// xhr.setRequestHeader("pplication/x-www-form-urlencoded");
//原型上的方法  发送ajax请求
//type:请求方式
//url:请求地址
//dataType：设置数据类型
//async:同步获异步
//cache:缓存设置
//success：成功的回调，响应主体内容已经反回了
````

**`9.事件`**
>jq对象.事件名称(function(e){});
>jq对象.on("事件名称”，“代理对象”，数据，function(){});

>当前元素已经绑定了某个事件再次去触发
>>jq对象.事件();
>>jq对象.trigger("事件名称")

### DOM回流和DOM重绘
	浏览器先加载HTML,CSS,JS,形参DOM树
	重绘:一般是当前页面样式发生改变div.style.color = "red";
	避免重绘:尽量使用className去操作div.className = "bg";

	回流:当前HTML文档的结构发生改变,操作节点,元素显示隐藏,宽度高度等改变
	一般引起DOM的回流更多是在数据绑定中

	数据绑定的方式
	字符串拼接
	缺点:会引发多次DOM回流,每次引发DOM回流刘览器都会重新计算页面结构

	文档碎片:不占性能
	好处:减少DOM回流次数
	文档碎片比较多也会占用浏览器的性能,最后我们用完的时候手动释放
	//createDocumentFragment():创建文档碎片,是固定的写法
	var frag = document.createDocumentFragment();
	//一般真实项目中字符串拼接的方式+文档碎片的方式

	示列代码
	var frag = document.createDocumentFragment();
	for (var i = 0;i<100;i++){
	var curLi = document.createElement("li");
	curLi.innerHTML = "皮卡丘"+"丶"+i+"号";
	frag.appendChild(curLi);
	}
	//只回流一次
	document.body.appendChild(frag);
	//手动释放
	frag = null;
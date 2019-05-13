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



>>
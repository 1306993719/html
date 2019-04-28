# 正则验证的封装函数

```html
//正则验证的封装
//参数：
//验证的类型
//验证的字符串
//返回值：true：表示合法；false：不合法

function check(type,str) {
	switch(type){
		case "email":var reg = /^\w{3,}@\w{2,}\.(com|cn|net|com.cn)$/;break;//终止函数,跳出
		case "phone": var reg = /^1\d{10}$/;break;
		case "card":var reg = /^[1-9]\d{16}(\d|X)$/i;break;
		case "post":var reg = /^[1-9]\d{5}$/;break;
		case "ip":var reg = /^((\d|[1-9]\d|1\d{2}|2[0-4]\d|25[0-5])\.){3}(\d|[1-9]\d|1\d{2}|2[0-4]\d|25[0-5])$/i;break;
		case "birthday":reg = /^(\d{4}\-(0[1-9]|1[0-2])\-\d{2}|\d{4}\.(0[1-9]|1[0-2])\.\d{2}|\d{4}\.(0[1-9]|1[0-2])\.\d{2})$/i;break;
		case "user":var reg = /^^[a-zA-Z_][a-zA-Z0-9_]{5,15}$/;break;
		default:;
	}
	return reg.test(str);
}
```

# 绑定事件的函数封装

```html
//绑定事件

//参数：
//dom对象，
//事件类型 不带on 
//事件处理函数
//是否捕获

//返回值：无

function addEvent1902(domObj,eventType,func,isCapture) {
	if(domObj.addEventListener){
		domObj.addEventListener(eventType,func,isCapture);
	}else if(domObj.attachEvent){
		domObj.attachEvent("on"+eventType,func);
	}else{
		var str ="on"+eventType; 
		domObj[str] = func;
	}
}
```

# 运动的封装函数

```html
//功能封装：运动
//参数：DOM元素，属性名，初始值，结束值，步长，时间间隔。
//返回值：无

function mover01(domObj,attr,startValue,endValue,step,timerSpace){

	let value = startValue;
	//方向：
	let direction = endValue>startValue?1:-1;//方向

	let myTimer = setInterval(function(){
		value+= direction*step;//方向*步长	
		if(direction==1?value>=endValue:value<=endValue){
			value = endValue;
			clearInterval(myTimer);
		}
		/*
		if(endValue>startValue){
			if(value>=endValue){
				value = endValue;
				clearInterval(myTimer);
			}
		}else{
			if(value<=endValue){
				value = endValue;
				clearInterval(myTimer);
			}
		}*/
		if(attr=='opacity'){
			domObj.style[attr] = value;
		}else{
			domObj.style[attr] = value+"px";	
		}
	},timerSpace);
}

//运动：
// 让一个物体花多长时间，从当前位置到指定位置
//参数：DOM元素，属性名，结束值，总时间

function mover02(domObj,attr,endValue,timeLong){
	let startValue = parseInt(getStyle(domObj,attr));
	//已知timeLong；
	let timerSpace= 16;
	let long = Math.abs(endValue-startValue);
	let step = long/(timeLong/timerSpace)  //long/(走多少次次数)
	mover01(domObj,attr,startValue,endValue,step,timerSpace);
}


//多属性运动的封装

//运动：
// 让一个物体花多长时间，从当前位置到指定位置

//参数：DOM元素，josn对象表示多个属性的结束值，总时间

// mover03($("#box"),{"width":500,"height":800},3000);

function mover03(domObj,obj,timeLong){
//	let startValue = parseInt(getStyle(domObj,attr));
	//多个起始值
	let qishizhis = {}
	for(let key in obj){//循环json对象，每循环一次，key是属性名
		qishizhis[key] = parseInt(getStyle(domObj,key));
	}

	//已知timeLong；
	let timerSpace= 16;
	//总路程
	// let long = Math.abs(endValue-startValue);
	let longs = {};
	for(let key in obj){//循环json对象，每循环一次，key是属性名
		longs[key] = Math.abs(obj[key]-qishizhis[key]);
	}

	// let step = long/(timeLong/timerSpace)  //long/(走多少次次数)
	let steps={}	
	for(let key in obj){//循环json对象，每循环一次，key是属性名
		steps[key] = longs[key]/(timeLong/timerSpace);
	}
	//当前值
	// let value = startValue;
	let values = {};
	for(let key in obj){//循环json对象，每循环一次，key是属性名
		values[key] = qishizhis[key];
	}

	//方向：
	// let direction = endValue>startValue?1:-1;//方向
	let fangxiangs = {};
	for(let key in obj){//循环json对象，每循环一次，key是属性名
		fangxiangs[key] = obj[key]>qishizhis[key]?1:-1;
	}

	let myTimer = setInterval(function(){
		// value+= direction*step;//方向*步长	
		for(let key in obj){//循环json对象，每循环一次，key是属性名
			values[key] += fangxiangs[key]*steps[key];
		}

		// // if(direction==1?value>=endValue:value<=endValue){
		// 	value = endValue;
		// 	clearInterval(myTimer);
		// }

		let isEnd = false;
		for(let key in obj){
			if(fangxiangs[key]==1?values[key]>=obj[key]:values[key]<=obj[key]){
				values[key] = obj[key];
				isEnd = true;
			}
		}
		if(isEnd==true){
			clearInterval(myTimer);
		}

		// domObj.style[attr] = value+"px";
		for(let key in obj){
			if(key=='opacity'){
				domObj.style[key] = values[key];
			}else{
				domObj.style[key] = values[key]+"px";
			}
		}
	},timerSpace);
}


//两张图片的淡入淡出
function fadeInOut(domObjIn,domObjOut,timeLong){
	//已知timeLong；
	let timerSpace= 16;
	let long = 1;
	let step = long/(timeLong/timerSpace) 
	
	let opacity = 0;

	let myTimer = setInterval(function(){
		opacity +=step;

		if(opacity>=1){
			opacity = 1;
			clearInterval(myTimer);
		}

		domObjIn.style.opacity = opacity;
		domObjOut.style.opacity = 1-opacity;

	},timerSpace);

}

// document.getElementById("box").t

//获取dom节点的样式属性(兼容性写法)
//参数：dom节点（对象），样式属性
//返回值：样式属性对应的值

function getStyle(domObj,attr) {
	if(domObj.currentStyle){//dom对象具有currentStyle属性,不为null
		return domObj.currentStyle[attr]
	}else{
		var obj = window.getComputedStyle(domObj);
		return obj[attr];
	}
}
```

# 获取dom节点的样式属性(兼容性写法)

```html
//获取dom节点的样式属性(兼容性写法)
//参数：dom节点（对象），样式属性
//返回值：样式属性对应的值

function getStyle(domObj,attr) {
	if(domObj.currentStyle){
		return domObj.currentStyle[attr]
	}else{
		var obj = window.getComputedStyle(domObj);
		return obj[attr];
	}
}
```

# 日期的封装函数

```html
// 1，输出自己的日期格式

//功能：把日期对象转成指定的日期格式的字符串
//参数：日期，分隔符
//返回值：字符串

function dateToStr(d,sep){
	var str="";
	if(sep==undefined){
		str += d.getFullYear()+"年";
		str += (d.getMonth()+1)+"月";
		str += d.getDate()+"日";
	}else{
		str += d.getFullYear()+sep;
		str += (d.getMonth()+1)+sep;
		str += d.getDate();
	}
	return str;
}

// var d =new Date();
// dateToStr(d,',');


// 2，转换周几为汉字

function toWeek(num){
	var result;
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
	return result;
}


// 3，计算两个日期天数差
//功能：求两个日期相差的天数
//参数：日期1(如：2019-4-1 23:25:21 ) ，日期2（2020-5-15 01:25:21）
//返回值：天数

// 4-15 23:20:10   4-17 23:21:00

function differentDate(d1,d2) {
	d1.setHours(0);
	d1.setMinutes(0);
	d1.setSeconds(0);
	d1.setMilliseconds(0);

	d2.setHours(0);
	d2.setMinutes(0);
	d2.setSeconds(0);
	d2.setMilliseconds(0);

	return (d1.getTime()-d2.getTime())/(24*3600*1000);
}


// 4，计算两个日期的月份差 (year2-year1)*12+(month2-month1);

//功能：求两个日期相差的月份数
//参数：日期1(如：2019-4-1) ，日期2（2020-2-15）
//返回值：月份相差数

function differentMonth(d1,d2){
	return (d1.getFullYear()-d2.getFullYear())*12+(d1.getMonth()-d2.getMonth())
}
```

# n位的数字验证码的函数封装

```html
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
```
# 面向对象的轮播图封装

```html
//面向对象编程思想：
//类：轮播图

function Banner(boxDom,width,height,imgs,douIsCircle,douSize,douColor,douHighColor,douPostion,timeSpace){
	this.boxDom = boxDom;
	this.imgDoms = [];//存放所有图片的dom，img标签
	this.width = width;
	this.height = height;
	// this.left = left;
	// this.top = top1;
	this.imgs = imgs;//要播放的图片路径数组;如:['img/1.jpg','img/2.jpg']
	this.douIsCircle = douIsCircle;//豆豆是不是圆。
	this.douSize = douSize;//豆豆的大小
	// this.douSpace = douSpace;//豆豆的间隔
	this.douColor = douColor;
	this.douHighColor = douHighColor;//高亮
	this.douPostion = douPostion;//豆豆的位置，上，右，下，左
	this.timeSpace = timeSpace;
	this.myTimer = null;//轮播图的定时器

	this.currOrd = 0;
	this.createUI();
	this.addEvent();
	this.autoPlay();
}

//创建轮播图中所有的DOM元素
Banner.prototype.createUI = function(){
	//1、创建所有图片
	for(let i in this.imgs){
		let imgDom = document.createElement("img");
		imgDom.src = this.imgs[i];
		imgDom.style.cssText = `position: absolute;
				left:0px;
				top:0px;
				width: ${this.width}px;
				height: ${this.height}px;
				opacity: 0;`;
		if(i=="0"){
			imgDom.style.opacity = 1;
		}
		this.boxDom.appendChild(imgDom);
		this.imgDoms.push(imgDom);
	}

	//2、创建豆豆
	//1）、豆豆的ul
	let ulDom = document.createElement("ul");
	ulDom.style.cssText =`
				margin:0;
				padding:0;
				position: absolute;
				list-style: none;
				z-index: 3;`;

	switch(this.douPostion){
		case "上":{
			ulDom.style.top = this.height*0.05+"px";
			ulDom.style.left = (this.width-(this.douSize*2*this.imgs.length))/2 +"px";
		}break;
		case "下":{
			ulDom.style.bottom = this.height*0.05+"px";			
			ulDom.style.left = (this.width-(this.douSize*2*this.imgs.length))/2+"px";
		}break;
		case "左":ulDom.style.left = this.width*0.05+"px";break;
		case "右":ulDom.style.right = this.width*0.05+"px";break;
	}
	this.boxDom.appendChild(ulDom);

	//2）、豆豆 li
	for(let i in this.imgs){
		let liDom = document.createElement('li');

		liDom.style.cssText =`
				margin:0;
				padding:0;
				float:left;
				width:${this.douSize}px;
				height: ${this.douSize}px;
				margin-right: ${this.douSize/2}px;
				margin-left: ${this.douSize/2}px;
				background-color: ${this.douColor};`;
		if(this.douIsCircle){
			liDom.style.borderRadius = '50%';
		}
		if(i=="0"){
			liDom.style.backgroundColor = this.douHighColor;
		}
		ulDom.appendChild(liDom);
	}
}		

Banner.prototype.autoPlay = function(){
	let liDoms = this.boxDom.lastElementChild.children;
	if(this.myTimer!=null){
		return;
	}
	this.myTimer = setInterval(()=>{
		//一、数据处理
		//淡出的图片序号
		let outOrd = this.currOrd;		
		this.currOrd++;

		if(this.currOrd>this.imgs.length-1){
			this.currOrd = 0;
		}

		//二、改变外观

		fadeInOut(this.imgDoms[this.currOrd],this.imgDoms[outOrd],1000);
		//变豆豆
		for(let i=0;i<liDoms.length;i++){
			liDoms[i].style.backgroundColor = this.douColor;
		}
		liDoms[this.currOrd].style.backgroundColor = this.douHighColor;		
	},this.timeSpace);
}

Banner.prototype.stopPlay=function(){
	clearInterval(this.myTimer);
	this.myTimer = null;
}

Banner.prototype.goImg=function(ord){
	let liDoms = this.boxDom.lastElementChild.children;
	
	//一、数据处理
	//淡出的图片序号
	let outOrd = this.currOrd;

	this.currOrd = ord;

	if(this.currOrd>this.imgs.length-1){
		this.currOrd = 0;
	}

	//二、改变外观

	fadeInOut(this.imgDoms[this.currOrd],this.imgDoms[outOrd],500);
	//变豆豆
	for(let i=0;i<liDoms.length;i++){
		liDoms[i].style.backgroundColor = this.douColor;
	}
	liDoms[this.currOrd].style.backgroundColor = this.douHighColor;
}

Banner.prototype.addEvent = function(){
	// //2、鼠标放在轮播图的盒子里，停止播放
	this.boxDom.onmouseenter = ()=>{
		this.stopPlay();
	}

	// //3、鼠标离开轮播图的盒子，继续播放
	this.boxDom.onmouseleave = ()=>{
		this.autoPlay();
	}

	// //4、点击某个豆豆，跳转到对应的图片上
	let liDoms = this.boxDom.lastElementChild.children;
	for(let i=0;i<liDoms.length;i++){
		liDoms[i].onclick = ()=>{
			this.goImg(i);
		};
	}
}
```
# n倍放大镜es3写法

```html
//1、放大镜
function BigMirror(obj){
	//放大镜对象的默认值
	let defaultObj = {
		boxDom:null,//放大镜所在的容器（需要放大的图片），由外部传入的
		mirrorDom:null,//放大镜的dom，需要内部创建的
		showDom:null,//放大效果，需要内部创建的
		width:100,
		height:100,
		color:"pink",
		opacity:0.5,
		mulitple:3
	}

	//属性
	for(let key in defaultObj){
		if(obj[key]==undefined){//没有如果传值，就是undefined；
			this[key] = defaultObj[key];
		}else{
			this[key] = obj[key];
		}
	}
	this.creatUI();
	this.addEvent();
}

//创建dom
BigMirror.prototype.creatUI = function() {
	//1、创建放大镜的div
	this.mirrorDom = document.createElement("div"); 
	this.mirrorDom.style.cssText = `position:absolute;
				left:0px;
				top:0px;
				width:${this.width}px;
				height:${this.height}px;
				background-color:${this.color};
				opacity:${this.opacity};
				display:none;
				`;
	this.boxDom.appendChild(this.mirrorDom);
	//2、创建放大效果的div
	this.showDom =  document.createElement("div"); 
	this.showDom.style.cssText =`
				position:absolute;
				left:${this.boxDom.offsetWidth+10}px;
				top:0px;
				width:${this.width*this.mulitple}px;
				height:${this.height*this.mulitple}px;
				background-image:${getStyle(this.boxDom,"backgroundImage")};
				background-size:${this.boxDom.offsetWidth*this.mulitple}px ${this.boxDom.offsetHeight*this.mulitple}px;
				display:none;`;

	this.boxDom.appendChild(this.showDom);
};

//this:必须出现在函数里（因为this是代名词，所以，this必须出现在一个环境里，此处的环境是函数）
// https://blog.csdn.net/jiang7701037/article/details/79153906
//1、当this所在函数是事件处理函数时，this是事件源
//2、当this所在函数是构造函数时，this是new出来的对象
//3、当this所在函数是类的方法，this是调用方法时的对象。

//this转移: this在不同的函数里代表的意思不同，这叫做this转移。
// https://blog.csdn.net/jiang7701037/article/details/79314864


BigMirror.prototype.addEvent = function(){
	
	let obj = this;//为了防止this转移，先把this赋给obj

	this.boxDom.onmouseenter = function(event){
		obj.mirrorDom.style.display = "block";
		obj.showDom.style.display = "block";
	}

	this.boxDom.onmouseleave = function(event){
		obj.mirrorDom.style.display = "none";
		obj.showDom.style.display = "none";
	}

	this.boxDom.onmousemove = function(event){
		let evt = event || window.event;
		//一、数据处理
		//1、改变数据
		let left1 = evt.pageX-this.offsetLeft-obj.mirrorDom.offsetWidth/2;
		let top1 = evt.pageY-this.offsetTop-obj.mirrorDom.offsetHeight/2;

		//2、处理边界
		if(left1<0){
			left1 = 0;
		}else if(left1>this.offsetWidth-obj.mirrorDom.offsetWidth){
			left1=this.offsetWidth-obj.mirrorDom.offsetWidth
		}

		if(top1<0){
			top1 = 0;
		}else if(top1>this.offsetHeight-obj.mirrorDom.offsetHeight){
			top1=this.offsetHeight-obj.mirrorDom.offsetHeight
		}

		//二、改变外观
		obj.mirrorDom.style.left = left1+"px";
		obj.mirrorDom.style.top = top1+"px";

		obj.showDom.style.backgroundPosition = `-${obj.mulitple*left1}px -${obj.mulitple*top1}px`;
	}
}
```

# n倍放大镜es6写法

```html
class BigMirror{
	constructor(obj){
		//放大镜对象的默认值
		let defaultObj = {
			boxDom:null,//放大镜所在的容器（需要放大的图片），由外部传入的
			mirrorDom:null,//放大镜的dom，需要内部创建的
			showDom:null,//放大效果，需要内部创建的
			width:100,
			height:100,
			color:"pink",
			opacity:0.5,
			mulitple:3
		}

		//属性
		for(let key in defaultObj){
			if(obj[key]==undefined){//没有如果传值，就是undefined；
				this[key] = defaultObj[key];
			}else{
				this[key] = obj[key];
			}
		}
		this.creatUI();
		this.addEvent();
	}

	creatUI(){

		//1、创建放大镜的div
		this.mirrorDom = document.createElement("div"); 
		this.mirrorDom.style.cssText = `position:absolute;
					left:0px;
					top:0px;
					width:${this.width}px;
					height:${this.height}px;
					background-color:${this.color};
					opacity:${this.opacity};
					display:none;
					`;
		this.boxDom.appendChild(this.mirrorDom);
		//2、创建放大效果的div
		this.showDom =  document.createElement("div"); 
		this.showDom.style.cssText =`
					position:absolute;
					left:${this.boxDom.offsetWidth+10}px;
					top:0px;
					width:${this.width*this.mulitple}px;
					height:${this.height*this.mulitple}px;
					background-image:${getStyle(this.boxDom,"backgroundImage")};
					background-size:${this.boxDom.offsetWidth*this.mulitple}px ${this.boxDom.offsetHeight*this.mulitple}px;
					display:none;`;

		this.boxDom.appendChild(this.showDom);
	}

	addEvent(){

		let obj = this;//为了防止this转移，先把this赋给obj

		this.boxDom.onmouseenter = function(event){
			obj.mirrorDom.style.display = "block";
			obj.showDom.style.display = "block";
		}

		this.boxDom.onmouseleave = function(event){
			obj.mirrorDom.style.display = "none";
			obj.showDom.style.display = "none";
		}

		this.boxDom.onmousemove = function(event){
			let evt = event || window.event;
			//一、数据处理
			//1、改变数据
			let left1 = evt.pageX-this.offsetLeft-obj.mirrorDom.offsetWidth/2;
			let top1 = evt.pageY-this.offsetTop-obj.mirrorDom.offsetHeight/2;

			//2、处理边界
			if(left1<0){
				left1 = 0;
			}else if(left1>this.offsetWidth-obj.mirrorDom.offsetWidth){
				left1=this.offsetWidth-obj.mirrorDom.offsetWidth
			}

			if(top1<0){
				top1 = 0;
			}else if(top1>this.offsetHeight-obj.mirrorDom.offsetHeight){
				top1=this.offsetHeight-obj.mirrorDom.offsetHeight
			}

			//二、改变外观
			obj.mirrorDom.style.left = left1+"px";
			obj.mirrorDom.style.top = top1+"px";

			obj.showDom.style.backgroundPosition = `-${obj.mulitple*left1}px -${obj.mulitple*top1}px`;
		}
	}
}
```

# 数组去重的封装函数

```html
//函数名：removeRepeat
//函数功能：把数组中重复的元素去除掉。（不能使用set）
//参数：有重复元素的数组，
//返回值：无重复元素的数组，
function removeRepeat(arr){
	var arr1 = [];
	for(var i in arr){
		if(arr1.indexOf(arr[i])==-1){
			arr1.push(arr[i]);
		}
	}
	return arr1;
}


//函数名：myconcat
// 函数名：myconcat
// 功能：把两个数组合并，并去掉重复的元素：（不能使用官方函数concat）
// 参数：两个数组
// 返回值：合并后，没有重复元素的数组；

function myconcat(arr1,arr2){
	var arr=[];
	for(var i=0;i<arr1.length;i++){
		arr.push(arr1[i])
	}
	for(var j=0;j<arr2.length;j++){
		arr.push(arr2[j])
	}
	return removeRepeat(arr)
}
```


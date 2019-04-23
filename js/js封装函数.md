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
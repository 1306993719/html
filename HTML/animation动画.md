# transition(过渡)

	兼容性:
		ie10+、谷歌、火狐、欧朋、safari.

	语法：
		transition:过渡属性 过渡时间 过渡延迟时间 过渡方式;
		
## transition-property (过渡属性)

	transition-property 设置的是具体属性，如果没有在本条属性中设置某个属性参与过渡，那么没有参与的属性就不会具有过渡效果。
​	如果没有设置transition-property 属性，那么标签的所有属性默认都会参与到过渡效果中来。
​	如果在设置transition-property属性的时候，想要让所有的属性都参与过渡，可以设置为*all*
​	如果在设置的时候，不想让任何属性参与进过渡效果，但是还必须设置这个属性，那么就可以将属性值设置为*none。*

	取值：
		all   所有发生变化的css属性都添加过渡
		列:  
			transition:all 1s;

		ident  指定发生过渡的css属性列表
		列: 
			transition:transform 3s,border-radius 2s,background 1s;

		none  没有元素发生过渡
		
## transition-duration(过渡时间)

	取值：
		0  默认值，不执行过渡，直接看到结果
		time  指定过渡动画执行的时间
		
## transition-delay(过渡延迟)

	在指定的时间之后再来执行变化的效果，单位：秒/s ; 毫秒/ms ;

	取值：
		0  默认值，不延迟	
		正数  按照设置的时间延迟执行动画
		负值  设置时间前的动画将会被截断
		
## transition-timing-function(过渡方式)

	取值：
		ease  默认值
		cubic-bezier	后面设置贝塞尔曲线的值
		linear  匀速运动
		ease-in  加速运动
		ease-out  减速运动
		ease-in-out  慢-快-慢
		
	都是贝塞尔曲线的值
	贝塞尔曲线图的网址：http://cubic-bezier.com
	
# css3 2D

## 相关属性

	transform : 2d/3d之间的转换
	transform-origin : 更改元素的基点  
	
## 相关属性值

	位移：
		translate(x,y)   沿着x y 移动元素/ translateX(n)  translateY(n)
		
	缩放：
		scale(x,y)  缩放  更改元素的宽度和高度 ,将宽度改为原来的x倍，高度改为原来的y倍 / scaleX(n) 更改宽度  scaleY(n)  更改高度
		
	旋转：
		rotate(angle)  旋转 
		
	倾斜：
		skew(x-angle,y-angle)  定义2D 倾斜转换 沿着x轴和y轴  / skewX(angle) 沿着x轴转换  skewY(angle) 沿着y轴
		
## transform-origin :更改元素的基点

	语法:
		transform-origin:(x轴值,y轴值)
		x轴: left | center | right | length | % 
		y轴: top | center | bottom | length | %
		
# CSS3 3D

## 相关属性

	transform:2d/3d之间的转换
	transform-origin:更改元素的基点
	transform-style:flat|preserve-3d 开启3d空间
	perspective 景深,一般值的范围在900px-1200px ,景深的值最好不要太夸张;更多的时候是用在父元素的身上。
	perspective-origin 景深基点
	backface-visibibility   背面隐藏
	
## 相关属性值：

	translateX | translateY | translateZ | translate3d(x,y,z)
	scaleX | scaleY | scaleZ | scale3d()
	rotateX(angle) | rotateY(angle) | rotateZ(angle)
	
## 开启3D空间

	transform-style:flat|preserve-3d 开启3d空间
	当属性值为flat的时候，网页是默认为2d空间的。
	
## rotate3d(x,y,z,a)

	x：是一个0到１之间的数值，主要用来描述元素围绕X轴旋转的矢量值；
	y：是一个０到１之间的数值，主要用来描述元素围绕Y轴旋转的矢量值；
	z：是一个０到１之间的数值，主要用来描述元素围绕Z轴旋转的矢量值；
	a：是一个角度值，主要用来指定元素在3D空间旋转的角度，如果其值为正值，元素顺时针旋转，反之元素逆时针旋转。 
		
## 3D缩放

	CSS3:
		3D变形中的缩放主要有scaleZ()和scale3d()两种函数，当scale3d()中X轴和Y轴同时为1，即scale3d(1,1,sz)，其效果等同于scaleZ(sz)。通过使用3D缩放函数，可以让元素在Z轴上按比例缩放。默认值为１，当值大于１时，元素放大，反之小于１大于0.01时，元素缩小。

	scale3d(sx,sy,sz)
		sx：横向缩放比例；
		sy：纵向缩放比例；
		sz：Z轴缩放比例；

	scaleZ(s)
		s：指定元素每个点在Z轴的比例。 
		
	注：
		scaleZ()和scale3d()函数单独使用时没有任何效果，需要配合其他的变形函数一起使用才会有效果
		
# animation动画

	语法：
		animation:动画名称 动画执行时间 动画延迟执行时间 动画播放次数 动画执行方式 动画运动状态 动画运动方向 动画时间之外的状态;

	在使用animation动画之前先要设置好动画关键帧，语法如下：
	@keyframes 动画名称{
		0%{
			属性:属性值;
			...
		}
		20%{
			属性:属性值;
			...
		}
			...
		100%{
			属性:属性值;
		}
	}

	@-webkit-keyframes 动画名称{
		from{
			属性:属性值;
			...
		}
		20%{
			属性:属性值;
			...
		}
			...
		to{
			属性:属性值;
			...
		}
	}	
		
## animation-name(调用关键帧)

	列:
		animation:box 1s;

	注：
		此处动画名称要和@keyframes中动画名称一致	
		
## animation-duration(设置完成时间)

	取值：
	0  默认值，不执行动画
	time   正数，单位为s或ms
	
## animation-delay(延迟)

	取值：
	0  不延迟
	正数   按照指定的时间延迟执行动画
	负值   设置时间前的动画将会被截断
	
## animation-iteration-count(动画应该播放的次数)

	取值：
	number  正整数
	infinite  无限循环播放
	
## animation-play-state(暂停/运行)

	取值：
		running  默认值，运动
		paused   暂停

## animation-timing-function(动画的速度曲线)

	取值：
		ease 默认值
		linear 线性效果，匀速运动
		ease-in   加速运动，渐显效果
		ease-out  减速运动，渐隐效果
		ease-in-out  慢-快-慢
		step-start  马上转跳到动画结束状态，或者下一帧关键帧
		step-end  保持动画开始时的状态，当动画结束时，转跳到动画结束状态
		steps(n,start|end)  n为动画分几个阶段完成
		
## animation-direction(规定是否该轮流反向播放动画)

	取值：
		normal  正常方向运动
		reverse  与normal方向相反
		alternate  正反方向交替运动，奇数次正方向，偶数次反方向
		alternate-reverse    奇数次反方向，偶数次正方向
		
## animation-fill-mode(设置动画时间之外的状态)

	取值：
		none  不设置动画时间之外的状态
		forwards  保持动画结束时的状态
		backwards  保持动画开始时的状态
		both  遵循forwards和backwards两个规则

	扩展：
		隐藏翻转元素的背面
	语法：
		backface-visibility:hidden;
		
## transition和animation的区别

	1.transition动画执行需要触发条件，无法再页面加载完成后自动执行
	animation动画不需要触发条件，可以在页面加载完成后自动执行

	2.transition动画默认触发一次，只能执行一次，再次执行需要再次触发
	animation动画可以指定动画播放次数，或者无限循环播放

	3.transition动画只有开始和结束两个状态，不能定义中间的状态
	animation动画可以像flash一样定义动画的关键帧
		
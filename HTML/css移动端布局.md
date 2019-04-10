## 移动端相关概念
	1.屏幕尺寸
		屏幕尺寸是指屏幕对角线的长度，单位为英寸，1英寸=2.54厘米

	常见移动端设备，屏幕尺寸：
		iphone4   3.5英寸
		iphone5   4英寸
		iphone6,6s,7,8    4.7英寸
		iphone6plus,7plus,8plus   5.5英寸
		iphoneX    5.8英寸

	2.屏幕分辨率(像素分辨率)
		屏幕分辨率是指横纵方向上的像素点数，单位为px，1px=1个像素点

	常见移动端设备，屏幕分辨率 (纵向*横向)
		iphone4                    960*640   
		iphone5                    1136*640
		iphone6,6s,7,8             1334*750
		iphone6plus,7plus,8plus    1920*1080
		iphoneX                    2436*1125

	3.ppi
		ppi是指屏幕上每英寸可以显示的像素点的数量，即屏幕像素密度，单位为ppi(pixels per inch)

	4.dpr
		dpr(devicepixelratio)中文译为设备像素比，是设备物理像素与设备独立像素的比值，即
		DPR = 物理像素 / 逻辑像素
		DPR = 屏幕分辨率 / 设备实际尺寸

	常见移动端设备dpr值
		iphone4,iphone5,iphone6,6s,7,8   dpr=2
		iphone6plus,7plus,8plus     dpr=3

	5.viewport设置

	在移动端，一般视图窗口的宽度大于手机可视区域的宽度，我们需要让视图窗口的宽度等于设备的宽度，即
		<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">

	快捷键： meta:vp   tab键
	
## 移动端常见布局方案及其特点
	1.100%布局(流式布局)
		特点：
			不管分辨率怎么变，顶部和底部的bar高度和位置都不变
			文字流式，控件弹性，图片等比缩放
			典型案例：拉勾网

	2.等比例缩放布局(rem布局)
		特点：
			使用rem为主要单位进行页面布局，很好的实现了在不同设备上页面等比例缩放
			典型案例：网易

	3.混合布局
		特点：
			将多种布局方案(flex布局，圣杯布局等)，多种单位(px,百分比,rem)混合在一起使用来实现移动端屏幕适配的方案
		典型案例：淘宝网	
	
## 移动端相关单位
	1.px(像素)
		相对于屏幕分辨率而言

	2.em
		相对于父元素字体大小的单位，默认情况下 1em = 16px

	3.rem
		相对于根元素字体大小的单位，默认情况下 1rem = 16px

	注： 
		16px = 1em = 100% = 12pt = medium
		9pt = 12px
	
	4.vw
		vw(viewport width)是指视窗宽度
		1vw = 视窗宽度的1%

	注：
		vh  视窗高度
		vmin  vw和vh中较小值
		vmax  vw和vh中较大值

## 标准盒模型和怪异盒模型
	标准盒模型总宽度 = width + 左右padding + 左右border + 左右margin
	标准盒模型总高度 = height + 上下padding + 上下border + 上下margin
	怪异盒模型总宽度 =  width + 左右margin (width包含了padding和border)
	怪异盒模型总高度 = height + 上下margin (height包含了padding和border)

	注：
		当网页没有添加文档声明时，就会触发某些浏览器(IE6)的怪异模式

## box-sizing的可选属性值有哪些及其含义？
	box-sizing:content-box; (默认值，以标准盒模型的状态显示)
	box-sizing:border-box; 触发怪异盒模型		
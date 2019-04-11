## css3变形
	语法：
		transform:rotate(旋转)|scale(缩放)|skew(倾斜)|translate(位移);

	1.rotate(旋转)
		a) rotateX(180deg)  沿x轴旋转  等价于3d空间沿x轴旋转  rotate3d(1,0,0,180deg)
		b) rotateY(-180deg) 沿y轴旋转  等价于3d空间沿y轴旋转  rotate3d(0,1,0,-180deg)
		c) rotateZ(180deg)  沿z轴旋转  等价于3d空间沿z轴旋转  rotate3d(0,0,1,180deg)
		d) rotate(90deg)    2d空间的旋转，正值顺时针，负值逆时针

	注：
		旋转的单位为角度，即deg

	2.scale(缩放)
		a) scaleX(1.5)  
			沿x轴放大或缩小，默认值为1，大于1时放大，小于1时缩小，当为0时，元素会被隐藏
		b) scaleY(0.5)
			沿y轴放大或缩小
		c) scaleZ(1.5)  
			沿z轴放大或缩小
		d) scale(1.5)  当不指定轴时，x轴和y轴同时缩放
		e) scaleX(-1.5) 或 scaleY(-0.5) 或 scale(-1.5)
		当设置为负值时，先翻转后缩放

	3.skew(倾斜)
		a) skewX(30deg)  沿x轴倾斜
		b) skewY(-30deg)  沿y轴倾斜
		c) skew(30deg)  不指定轴时，默认沿x轴倾斜
		d) skew(30deg,30deg)  或 skewX(30deg) skewY(30deg)     x轴和y轴同时倾斜

	4.translate(位移)
		a) translateX(100px)  沿x轴位移，正值向右，负值向左
		b) translateY(-100px)  沿y轴位移，正值向下，负值向上
		c) translateZ(100px)   沿z轴位移，正值向前，负值向后
		d) translate(100px)  默认不指定轴时，沿x轴位移
		e) translate(100px,100px)  或 translateX(100px) translateY(100px)    x轴和y轴同时位移
		
	★ 使用css3变形的方式实现未知大小的元素在屏幕窗口水平垂直都居中
		元素{
			position:fixed;
			left:50%;
			top:50%;
			transform:translateX(-50%) translateY(-50%);
		}

	★ 使用css3变形的方式实现未知大小的子元素在父元素中水平垂直都居中
		父元素{
			position:relative;
		}
		子元素{
			position:absolute;
			left:50%;
			top:50%;
			transform:translate(-50%,-50%);
		}		
		
## 变形综合
	我们可以将多个变形方式放在一起使用，顺序不同，效果有可能不同，例如
	eg1: 
		transform:rotate(360deg) scale(2);
		transform:scale(2) rotate(360deg);
		顺序不同，效果相同

	eg2:
		transform:rotate(360deg) translateX(100px);
		transform:translateX(100px) rotate(360deg);

		顺序不同，效果不同		
		
## 改变变形元素中心点位置
	语法：
		transform-origin:left|center|right|百分比  top|center|bottom|百分比;	

## 设置元素变形的类型
	语法：
		transform-style:flat(默认值)|preserve-3d;
		flat  2d空间的变形
		preserve-3d    3d空间的变形
		
## 透视，视角，井深
	语法：
		perspective:数值+单位;

	作用：
		设置3d效果的强度或观察者距离物体的距离
		
	eg； 
		父元素{perspective:1000px;}
		子元素{transform:perspective(1000px) rotateY(60deg);}		
		
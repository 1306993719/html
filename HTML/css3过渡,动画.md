## transition(过渡)
	语法：
		transition:过渡属性 过渡时间 过渡延迟时间 过渡方式;

	1.transition-property (过渡属性)

	取值：
		all   所有发生变化的css属性都添加过渡

	eg:  
		transition:all 1s;
		ident  指定发生过渡的css属性列表

	eg: 
		transition:transform 3s,border-radius 2s,background 1s;
		none  没有元素发生过渡

	2.transition-duration(过渡时间)
	取值：
		0  默认值，不执行过渡，直接看到结果
		time  指定过渡动画执行的时间

	3.transition-delay(过渡延迟执行时间)
	取值：
		0  默认值，不延迟
		正数  按照设置的时间延迟执行动画
		负值  设置时间前的动画将会被截断

	4.transition-timing-function(过渡方式)

	取值：
		ease  默认值
		linear  匀速运动
		ease-in  加速运动
		ease-out  减速运动
		ease-in-out  慢-快-慢
		
## animation动画
	语法：
		animation:动画名称 动画执行时间 动画延迟执行时间 动画播放次数 动画执行方式 动画运动状态 动画运动方向 动画时间之外的状态;

	说明：
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

	1.animation-name(定义动画名称)
		eg:
			animation:box_ani 1s;

	注：
		此处动画名称要和@keyframes中动画名称一致

	2.animation-duration(动画执行一次所需时间)

		取值：
			0  默认值，不执行动画
			time   正数，单位为s或者ms

	3.animation-delay(动画播放前的延迟时间)

		取值：
			0  不延迟
			正数   按照指定的时间延迟执行动画
			负值   设置时间前的动画将会被截断

	4.animation-iteration-count(动画循环播放的次数)

		取值：
			number  正整数
			infinite  无限循环播放

	5.animation-play-state(动画运动状态)

		取值：
			running  默认值，运动
			paused   暂停

	eg:  
		.box{animation:box_ani 3s infinite;}
		.box:hover{animation:box_ani 3s infinite paused;}

	6.animation-timing-function(动画执行方式)

		取值：
			ease 默认值
			linear 线性效果，匀速运动
			ease-in   加速运动，渐显效果
			ease-out  减速运动，渐隐效果
			ease-in-out  慢-快-慢
			step-start  马上转跳到动画结束状态，或者下一帧关键帧
			step-end  保持动画开始时的状态，当动画结束时，转跳到动画结束状态
			steps(n,start|end)  n为动画分几个阶段完成

	7.animation-direction(动画运动方向)

		取值：
			normal  正常方向运动
			reverse  与normal方向相反
			alternate  正反方向交替运动，奇数次正方向，偶数次反方向
			alternate-reverse    奇数次反方向，偶数次正方向

	8.animation-fill-mode(设置动画时间之外的状态)

		取值：
			none  不设置动画时间之外的状态
			forwards  保持动画结束时的状态
			backwards  保持动画开始时的状态
			both  遵循forwards和backwards两个规则

		扩展：
			隐藏翻转元素的背面

		语法：
			backface-visibility:hidden;

	★ transition和animation的区别

	1.transition动画执行需要触发条件，无法再页面加载完成后自动执行

	  animation动画不需要触发条件，可以在页面加载完成后自动执行

	2.transition动画默认触发一次，只能执行一次，再次执行需要再次触发

	  animation动画可以指定动画播放次数，或者无限循环播放

	3.transition动画只有开始和结束两个状态，不能定义中间的状态

	  animation动画可以像flash一样定义动画的关键帧	

## BFC
	1.概念
		BFC——block formatting context,中文译为"块级格式化上下文"，是一个独立的渲染区域

	2.如何触发BFC
		a) float除none以外的其他值(left,right)
		b) overflow除visible以外的其他值(auto,scroll,hidden)
		c) 设置display为table-cell,table-caption,inline-block,flex
		d) 设置position属性值为absolute,fixed

	3.BFC特性
		a).浮动的元素会被父级计算高度（父级触发了BFC）
		b).非浮动元素不会覆盖浮动元素位置（非浮动元素触发了BFC）
		c).margin不会传递给父级（父级触发了BFC）
		d).两个相邻元素上下margin会重叠（给其中一个元素增加一个父级，然后让他的父级触发BFC）

	4.BFC作用
		a) 解决margin叠加问题
		b) 解决高度塌陷问题
		c) 用于布局

	与浮动元素相邻的已生成BFC的元素不能与浮动元素互相覆盖。利用该特性可以作为多列布局的一种实现方式	  
		
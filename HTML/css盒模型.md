# css盒模型的概念及组成

css盒模型是css的基石，每个html元素都有自己的盒模型，css盒模型就是用来设置元素之间的相关位置关系。
css盒模型是由content（主体部分）, padding(补白或填充)，border(边框)，margin（外边距）；

## content

	语法：
		width:数值+单位;
        height:数值+单位;

	注：
		当设置宽高除0以外的其他值时，都必须添加单位
		
## padding

	a）可以单独设置某个方向的padding值
	padding-left:20px;   
	padding-right:15px;
	padding-top:10px;
	padding-bottom:20px;

	b）使用padding属性的简写方式
	padding:20px;    上下左右均为20px
	padding:20px 10px;    第一个值代表上下为20px，第二个值代表左右为10px
	padding:30px 5px 10px;   第一个值代表上为30px，第二个值代表左右为5px，第三个值代表下为10px
	padding:30px 20px 10px 5px;  按照顺时针方向依次为上30px，右20px，下10px，左5px

	注：
		I.padding不允许设置负值
		II.背景可以延伸到padding区域
		III.当需要调整子元素在父元素中的位置关系时，通过给父元素添加padding来实现
		IV.如果元素设置了宽高，那么设置padding后要在原来宽高的基础上减去设置的padding值，保证总宽高不变
		
## border(边框)

	a) 边框样式

	语法：
		border-style:solid(实线)|dashed(虚线)|dotted(点线)|double(双线);

	b) 边框颜色

	语法：
		border-color:颜色值;

	c) 边框宽度

	语法：
		border-width:数值+单位;

	d) border属性简写方式

	语法：
		border: 宽度  线型  颜色;

	eg: 
		border:3px solid blue;

	e) 还可以单独设置某个方向的边框

	语法： 
		border-top:3px solid red;   (top可以根据具体需求更改为left,right,bottom)

	注：
		去掉某个方向的边框：
		border-left:none; 或 border-left:0;  

	注： 
		I. 背景可以延伸到border区域
        II.如果元素本身设置了宽高，设置border值后要在原来宽高的基础上减去设置的border值，保证总宽高不变	
		
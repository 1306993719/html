# DOM

## 文本节点与节点过滤
	创建文本节点的代码
		document.createTextNode（”文本节点包含的文本内容”）
	传入父节点和需要的节点的类型，返回复合要求的子节点
		function filternode(node,data){
			var arr=[];
			for(var i=0;i<node.childNodes.length;i++){
				if(node.childNodes[i].nodeType==data){
					arr.push(node.childNodes[i]);
				}
			}
			return arr;
		}

## 操作节点的属性
	node.属性名的方式访问和操作节点的属性，仅限于常规属性
	
	tagName:
		表示元素节点的标签名
		
	innerHTML:
		获取元素节点里的内容
		
	outerHTML:
		包含元素自身的标签.(非 W3C DOM 规范)
		
	innerText:
		获取元素内文本内容html标签被忽略（非 W3C DOM 规范）
		
	id:
		元素节点的 id 名称
		
	title:
		元素节点的 title 属性值（鼠标悬停时的提示）
		
	style:
		获取CSS行内样式属性值
		
	className：CSS元素的类 (不可以使用class)
	node. setAttribute(“属性名”,”值”) 的方式访问常规属性和自定义属性
	node. getAttribute(“属性名”) 的方式访问常规属性和自定义属性
	
	注：
		也可以在HTML中添加标签的自定义属性

## 操作样式

|          |  style全兼容   | currentStyle仅IE用 | getComputedStyle主流浏览器用 |
| :------: | :------------: | :----------------: | :--------------------------: |
| 行内样式 | 可获取，可修改 |       可获取       |            可获取            |
| 内部样式 |    无法获取    |       可获取       |            可获取            |
| 外部样式 |    无法获取    |       可获取       |            可获取            |

	对于样式获取尽量使用currentStyle和getComputedStyle 修改样式使用style 
	样式获取的兼容性处理：
	
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

## Style常见样式设置
	获取和设置行内样式获取和设置行内样式

|   CSS样式属性    |      Style      |
| :--------------: | :-------------: |
|      color       |      color      |
|    font-size     |    fontSize     |
|   font-family    |   fontFamily    |
| background-color | backgroundColor |
| background-image | backgroundImage |
|     display      |     display     |

	结论：
		一般情况下，css的样式属性中出现“-”号，则对应的style属性是：去掉“-”号，把“-”号后面单词的第一字母大写。如果没有“-”号，则两者一样。

## offset属性
	element.offsetHeight 通过计算得到的某个元素的高（元素必须出现在页面上）
	element.offsetWidth 通过计算得到的某个元素的宽（元素必须出现在页面上）
	element.offsetLeft 返回元素的水平偏移位置(基于最近的有定位的父元素，如果没有，就是body)
	element.offsetTop 返回元素的垂直偏移位置。 (基于最近的有定位的父元素，如果没有，就是body)
	element.offsetParent 返回元素的偏移容器。 (最近的有定位的父元素)
	
	如何计算某个元素距离页面的坐标
		getBoundingClientRect() 这个方法返回一个矩形对象，包含四个属性：left、top、right和bottom。分别表示元素各边与页面上边和左边的距离。
	
	var box=document.getElementById('box'); // 获取元素
	alert(box.getBoundingClientRect().top); // 元素上边距离页面上边的距离
	alert(box.getBoundingClientRect().right); // 元素右边距离页面左边的距离
	alert(box.getBoundingClientRect().bottom); // 元素下边距离页面上边的距离
	alert(box.getBoundingClientRect().left); // 元素左边距离页面左边的距离

## 下面的属性和方法可用于所有 HTML 元素上：
	element.accessKey 设置或返回元素的快捷键。
	element.appendChild() 向元素添加新的子节点，作为最后一个子节点。
	element.attributes 返回元素属性的 NamedNodeMap。
	element.childNodes 返回元素子节点的 NodeList。
	element.className 设置或返回元素的 class 属性。
	element.clientHeight 返回元素的可见高度。
	element.clientWidth 返回元素的可见宽度。
	element.cloneNode() 克隆元素。
	element.compareDocumentPosition() 比较两个元素的文档位置。
	element.dir 设置或返回元素的文本方向。
	element.firstChild 返回元素的首个子。
	element.getAttribute() 返回元素节点的指定属性值。
	element.getAttributeNode() 返回指定的属性节点。
	element.getElementsByTagName() 返回拥有指定标签名的所有子元素的集合。
	element.getFeature() 返回实现了指定特性的 API 的某个对象。
	element.getUserData() 返回关联元素上键的对象。
	element.hasAttribute() 如果元素拥有指定属性，则返回true，否则返回 false。
	element.hasAttributes() 如果元素拥有属性，则返回 true，否则返回 false。
	element.hasChildNodes() 如果元素拥有子节点，则返回 true，否则 false。
	element.id 设置或返回元素的 id。
	element.innerHTML 设置或返回元素的内容。
	element.insertBefore() 在指定的已有的子节点之前插入新节点。
	element.isDefaultNamespace() 如果指定的 namespaceURI 是默认的，则返回 true，否则返回 false。
	element.isEqualNode() 检查两个元素是否相等。
	element.isSameNode() 检查两个元素是否是相同的节点。
	element.isSupported() 如果元素支持指定特性，则返回 true。
	element.lang 设置或返回元素的语言代码。
	element.lastChild 返回元素的最后一个子元素。
	element.namespaceURI 返回元素的 namespace URI。
	element.nextSibling 返回位于相同节点树层级的下一个节点。
	element.nodeName 返回元素的名称。
	element.nodeType 返回元素的节点类型。
	element.nodeValue 设置或返回元素值。
	element.normalize() 合并元素中相邻的文本节点，并移除空的文本节点。
	element.offsetHeight 返回元素的高度。
	element.offsetWidth 返回元素的宽度。
	element.offsetLeft 返回元素的水平偏移位置。
	element.offsetParent 返回元素的偏移容器。
	element.offsetTop 返回元素的垂直偏移位置。
	element.ownerDocument 返回元素的根元素（文档对象）。
	element.parentNode 返回元素的父节点。
	element.previousSibling 返回位于相同节点树层级的前一个元素。
	element.removeAttribute() 从元素中移除指定属性。
	element.removeAttributeNode() 移除指定的属性节点，并返回被移除的节点。
	element.removeChild() 从元素中移除子节点。
	element.replaceChild() 替换元素中的子节点。
	element.scrollHeight 返回元素的整体高度。
	element.scrollLeft 返回元素左边缘与视图之间的距离。
	element.scrollTop 返回元素上边缘与视图之间的距离。
	element.scrollWidth 返回元素的整体宽度。
	element.setAttribute() 把指定属性设置或更改为指定值。
	element.setAttributeNode() 设置或更改指定属性节点。
	element.setIdAttribute()
	element.setIdAttributeNode()
	element.setUserData() 把对象关联到元素上的键。
	element.style 设置或返回元素的 style 属性。
	element.tabIndex 设置或返回元素的 tab 键控制次序。
	element.tagName 返回元素的标签名。
	element.textContent 设置或返回节点及其后代的文本内容。
	element.title 设置或返回元素的 title 属性。
	element.toString() 把元素转换为字符串。
	nodelist.item() 返回 NodeList 中位于指定下标的节点。
	nodelist.length 返回 NodeList 中的节点数。
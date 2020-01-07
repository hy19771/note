##BOM

###Offset


####获取元素的宽高
	offsetWidth/Height  是盒子自身的宽高加上padding+border的值
	offsetTop/left  是距离最近有定位的盒子的距离,没有定位就是相对于body
	offsetParent 返回的是距离最近有定位的父级,没有就是body

####行内样式
	element.style.styleName 只能获取行内样式

#####style可读写,offset只读

##事件对象

####返回鼠标点击的元素
	event.target

####返回事件的绑定对象
	event.currentTarget

####鼠标距离显示器的上边距
	event.screenY

####鼠标距离显示器的左边距
	event.screenX

####鼠标距离Body的上边距
	event.pageY

####鼠标距离Body的左边距
	event.pageX

####鼠标距离屏幕可视区域的上边距
	event.clientY

####鼠标距离屏幕可视区域的上边距
	event.clientX

####鼠标距离触发事件的元素的上边距
	event.offsetY

####鼠标距离触发事件的元素的左边距
	event.offsetY

###Scroll

####元素除去滚动条的宽度
	ele.scrollWidth

####元素除去滚动条的高度
	ele.scrollHeight

####可视区域距离元素的左边距
	ele.scrollLeft

####可视区域距离元素的上边距
	ele.scrollTop

####兼容代码,获取页面的卷入高度
	function sct() {
		return document.documentElement.scrollTop || window.pageYOffset || document.body.scrollTop || 0;
	}

###Client

####ClientWidth和ClientHeight要算上padding,不算border


####获取内联样式
	window.getComputedStyle(元素,伪类,没有就写null).样式

##Window对象

####内嵌页面
	<iframe src='初始页面路径' iframeborder='0' height='500' width='500' name='ifr'></iframe>	
	
####页面跳转
	window.open('https://www.baidu.com',iframe的name)

##Location对象

####页面跳转
	location.assign('https:www.baidu.com');

####页面重加载(刷新)
	location.reload();

####页面替换(不能后退)
	location.repalce('https://www.baidu.com)
	
##History对象

####历史记录长度
	history.length;

####加载历史记录中的上一个页面
	history.back()

####加载历史记录中的下一个页面
	history.forward()

####跳转到历史历史记录中的页面,或者新页面
	history.go(1||'https://www.baidu.com')

##Navigator对象

####浏览器名称
	navigator.appCodeName

####电脑操作系统 32/64
	navigator.platform

####头部值
	navigator.userAgent

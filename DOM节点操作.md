##DOM

####获取节点
	document.getElementById('idName')		根据id获取元素节点
	document.getElementByClassName('className')		根据class名获取元素节点,返回的是一个数组
	document.getElementByTagName('tagName')		根据标签名获取元素节点,返回的是一个数组
	document.querySeletor()			获取元素节点,class写成 '.className',id写成'#idName',标签民不用换
	document.querySeletorAll()		查找所有符合条件的元素节点,返回值是一个数组
	node.parentNode			获取该节点的父节点
	node.nextSibling			普通浏览器获取该节点的下一个节点
	node.nextElementSibling		该节点的下一个节点的兼容代码
	node.firstChild				获取第一个节点
	node.firstElementChild		获取第一个节点的兼容代码
	node.lastChild				获取最后一个子节点
	node.lastElementChild		获取该节点的最后一个子节点的兼容代码
	node.children				获取所有标签子节点
	node.childNodes				获取所有子节点,包括换行符

####判断节点类型
	nodeType === 1		元素节点
	nodeType === 2		属性节点
	nodeType === 3		文本节点
	nodeType === 8		注释节点	

####创建节点
	document.createElement('div')		创建一个div的节点

####插入节点
	parent.apprend(childNode)		父节点添加在最后添加一个子节点
	parent.insertBefore(参照节点,要放置的节点)

####删除节点
	parent.removeChild(要删除的节点)

####复制节点
	node.cloneNode()	只复制节点本身
	node.cloneNode(true) 	复制节点本身包括它的子节点

####节点内容操作
	node.innerText = '<p>傻逼<p>'	不解析p标签,直接打印出来
	node.innerHTML = '<p>傻逼<P>'	解析p标签,效果等同于插入一个子节点
	
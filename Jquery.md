#JQuery	

##筛选选择器

####匹配一个给定索引值的元素
	li:eq(index)

####匹配所有大于给定索引值的元素
	li:gt(index)

####匹配所有小于给定索引值的元素
	li:lt(index)

####匹配所有索引值为奇数的元素
	li:odd(index)

####匹配所有索引值为偶数的元素
	li:even(index)

####获取匹配的第一个元素
	li:first(index)

####获取匹配的最后一个元素
	li:last(index)

####属性修改
	$('img').attr('src','img/m1.jpgh) // 没有第二个参数就是获取,有就是设置

##类名操作

####添加
	$('img').addClass(类名)  

####删除
	$('img').removeClass(类名)	

####切换类
	$('img').toggleClass(类名)		//有则删除,无则添加

####判断是否有改类
	$('img').hassClass(类名)

####内容插入,不填内容就是获取
	$('ul').text(content)		//不解析标签
	$('ul').html(content)		//解析标签
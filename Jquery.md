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

####修改内容
	$('input').val('item')		//填东西就是修改,不填就是获取

####获取状态
	$('input').prop('checked',boolean)   //  boolean填了就是修改,不填就是获取 

##JQuery节点操作

####获取父节点
	$('.item').parent()
	$('.item').parents()		// 获取所有父元素
	$('.item').parent('html')			// 获取所有父元素直到html

####获取之前的兄弟元素

	$('item').prev()
	$('item').prevAll()		//  获取之前的所有元素
	$('item').prevUntil(item)		// 获取之前直到item的元素

####获取之后的兄弟元素
	$('item').next()
	$('item').nextAll()		//  获取之后的所有元素
	$('item').nextUntil(item)			// 获取之后直到item的元素

####获取除自身以外的兄弟元素
	$('item').siblings()

####获取子节点
	$('item').children()
	$('item').children().eq(index)		获取索引为index的子元素
	$('item').find(condition)    获取满足condition条件的子元素

##JQuery动画	 

###参数可以是 slow/normal/fast 第二个参数是动画执行结束后执行的函数

####显示和隐藏	

	$('item').hide(时间)
	$('item').show(时间,function)

####滑入和滑出
	$('item').sideDown(时间)
	$('item').sideUp(时间,function)


####滚动
	$(window).scroll(function) 监听对象滚动

####淡入和淡出
	$('item').fadeIn(时间)
	$('item').fadeOut(时间)
	$('item').fadeToggle(时间,function)  //如果是淡出的就会淡入,否之依然

####自定义动画	liner swing
	$('item').animate({ 'width’: '100px'},时间,运动方式,回调函数)

####停止动画  
	$('item').stop(是否停止所有动画,是否停止在当前动画的最后状态)

####插入节点
	$('parent').append($('child')		// 添加到最后
	$('child').appendTo($('parent')		// 被添加到最后
	$('item').prepend(内容或标签)		//在元素内容前添加内容或节点     
	$('item').before(要插入的元素)     	// 插在item之前
	$('item').after(要插入的元素)     	// 插在item之后

####复制节点
	$('item').clone()      

####删除节点
	$('item').empty()       //清空元素里的内容,一般是p,div
	$('item').html('')		//同上
	$('item').remove()		//删除当前节点


##JQuery BOM操作
	
####坐标值操作
	$('item').offset({left: 200,top: 100})    // 左移200,下移100
	$('item').position()		//获取相对定位的位置,只能获取
	$('item').width(100)		// 宽度设置成100,不填参数就是获取值
	$('item').height(100)		//高度设置成100,不填参数就是获取值
	$('item').scrollTop()		//获取和设置元素垂直方向的滚动位置,一般用于窗口

##JQuery绑定事件
	
####on绑定
	$('item').on(type,function)

####解绑事件
	$('item').off()
	$('item').off('click'); 解绑所有绑定的 click 事件，元素本身的事件不会被解绑
	$('item').off( 'click', “p” );	解绑	item里p标签的点击事件
	$('item').off( 'click',fn);		解绑叫fn的点击事件

####事件委托
	$('ul').on('click','li',fn) 把li的点击事件委托给ul绑定,效果还是li的点击事件一
	                                               
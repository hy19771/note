##CSS3

###兼容

	-moz-     /* 火狐等使用Mozilla浏览器引擎的浏览器 */
	-webkit-  /* Safari, 谷歌浏览器等使用Webkit引擎的浏览器 */
	-o-       /* Opera浏览器(早期) */
	-ms-      /* Internet Explorer (不一定) */ 	
	
####边框阴影
	box-shadow: 水平小 垂直大小 扩散范围 颜色;

####圆角
	border-radio: 左上 右上 右下 左下;

####背景图片
	background-image: url('') no-repeat 位置;
	background-origin: border-box,padding-box,content-box
	背景图可以显示在border中,内边距中,只能显示在content中
	background-clip: border-box,padding-box,content-box
	背景图在border可见,在内边距中可见,只能在内容区可见

####渐变
	background-image: linear-gradient(方向,颜色,颜色)
	方向可以写角度deg,left,默认加to兼容写法不用加to,颜色不限
	重复线性渐变: repeating-linear-gradient()
	径向渐变: radial-gradient:()

##转换

####转换中心
	transform-origin: bottom;

####旋转
	transform: rotate(30deg)

####移动
	transform: translate(100px,200px)

####缩放
	transform: scale(1.2)

####过渡
	transition: all ease 延迟时间 运行时间;

##动画Animation

####创建动画
	@keyframe animationName{
		from{}
		to{}
		或者
		0%{}
		100%{}
	}

####动画名称
	animation-name

####动画运行一周期时间
	animation-duration

####动画结束时,元素的位置
	animation-fill-mode: none(默认值)
	forwards		// 停留在最后一帧的位置
	backwards		// 停留在第一帧的位置
	both			// 设置元素停留在结束状态

####动画运功时间曲线
	animation-timing-function: ease(默认)
	linear		// 匀速
	ease		//	慢快慢
	ease-in		// 慢快
	ease-out	// 慢
	cubic-bezier(n,n,n,n)	//自定义时间曲线

####动画延迟时间
	animation-delay	

####动画重复次数
	animation-iteration-count: infinite(无限次)

####动画再次播放时是否重置
	animation-direction: normal(默认)  alternate(从结束处开始)	reverse(从尾部开始)

####动画播放状态
	animation-play-state; running  paused;

####简写
	animation: name duration timing-function delay iteration-count direction fill-mode;

####帧动画
	animation: name duration steps()

###动画监听事件

####动画开始
	circle.addEventListener('animationstart', function (){
		
	});

####动画结束
	circle.addEventListener('animationend', function (){
		
	});

####动画重复执行
	circle.addEventListener('animationiteration', function (){
		
	});
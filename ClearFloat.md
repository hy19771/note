# 清除浮动

#### 第一种方法：  给父盒子加边框



#### 第二种方法： 给父盒子加溢出隐藏

	overflow: hidden


#### 第三种方法： 伪类

	content: '';
	visible: hidden;
	height: 0;
	display: block;
	clear: both;


1213
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


# github上传代码的方法


#### 第一次上传

-  在要上传的项目文件夹里右键点击 git bash here
-  然后git init 初始化git本地仓库，git add .将所有文件添加到暂存区，
-  添加提交附加信息，例如‘首次提交之类的’ git commit -m '首次提交'
-  添加远程仓库依赖 git remote add origin url
-  如果依赖添加错误，运行 git remote rm origin删除依赖重新添加  
-  最后提交到仓库 git push origin master(分支名称)
##Vue

###指令

####插值表达式闪烁的解决
	
	<style>
		[v-clock]:{
			display: none;
		}
	</style>

	<p v-clock>{{message}}</p>

####填充文本
	<div v-text='message'></div>
	<div v-html='message'></div>
	<div v-pre>{{message}}</div> 显示原始信息,跳过解析
	<div v-once>{{message}}<div> 只编译一次,节省一点性能

####双向数据绑定
	<input type='text' v-model></input>
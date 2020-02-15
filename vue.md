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

####事件绑定传参事件对象(只能这样获取事件对象)
	@click='add(12,$event)'

####阻止冒泡
	<a @click.stop='to()'></a>

####阻止默认事件
	<a @click.prevent='to()'></a>

####阻止冒泡阻止默认
	<a @click.stop.prevent='to()'></a>

####点击元素自身触发
	<a @click.self='to()'></a>

####按键修饰符  @keyup.按键名='触发事件名'
	<input type='text' value='' @keyup.enter='submit'></input>

####自定义按键
	Vue.config.keyCodes.f2 =123;

####Class类名绑定
	<div :class='{active: isActive}'></div>

		data(){
			return{
				isActive: true
			}
		}

	<div :class='[activeClass]'></div>
		
		data(){
			return{
				activeClass: 'active'
			}
		}

####v-if和v-show
	v-if是控制元素是否渲染,v-show是控制元素是否显示(已渲染)

####v-for
	key的作用,帮助vue区分不同的元素,提高性能
	
	遍历对象		v-for="(value,key,index) in obj"

####表单修饰符
	v-model.number='num'  // 直接转化为数字
	v-model.trim='text'	  // 删除收尾多余的空格
	v-model.lazy='text'	  // 修改为change变化

###自定义指令

####全局添加自定义指令
	不带参  v-focus
	Vue.directive('focus',{
	   inserted: function(el){
		 el.focus():
		}
	 })
	
	带参		v-color='yellow'
	Vue.directive('color',{
		bind: function(el,binding){
			el.style.backgroundColor = binding.value
			}
		})
		
####组件内添加自定义指令
	directives:{
		指令名称: {
			bind: function(el,binds){
				el.style.backgroundColor = binds.value;
			}
		}
	}

###计算属性Conputed
	conputed:{
		reverse: function(){
			return this.message.split('').reverse.join('');
		}
	}

###Computed和methods的区别,计算会有缓存,依赖于data里的数据,而方法不会


	
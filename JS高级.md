##面向对象

###闭包

####延长作用域
	function f(){
		let a = 0;
		return function f1(a){
			a ++;
			console.info(a);		
		}
	}

	let fun =f();
	fun();	//	1
	fun();	//	2

####描述对象属性的属性
	Object.defineProperty(obj,attributeName,describe)
	
	Object.defineProperty(obj,'name',{
		enumerable: true,	// 可遍历
		writable: true,		//可修改
		configurable:true,	// 可配置
		value: 'micale'
	})

	Object.defineProperties(user, {
  		name: { value: "John", writable: false },
 	 surname: { value: "Smith", writable: false },
 	// ...
	});

####获取对象的所有属性,无论是否可遍历
	Object.getOwnPropertyDescriptor(obj,'age')	//单独获得某一属性
	Object.getOwnPropertyDescriptors(obj)

###原型
	
####原型上加属性或方法
	Person.proptype.name = '李四'
	person.proptype.run = function

####获取实例对象的原型对象
	实例对象._proto_
	Object.getProptypeOf(实例对象)

####获取实例对象的元素集合
	Object.keys(实例对象)

####Call和Apply
	obj = {
		name: '李白'
	}
	var name = '杜甫'

	function sayName(sex) {
		console.info(this.name,sex)
	{

	sayName();	// 杜甫
	sayName.call(obj,sex)	// 李白
	sayName.apply(obj,[sex])	//李白
##数组的常用方法
	
	arr.length  		数组的长度
	arr.push()    		在数组的末尾添加一个元素
	arr.pop()    		从数组最后开始删除一个元素
	arr.shift()   		在数组的开始处删除一个元素
	arr.unshift()  		在数组的开始处添加一个元素
	arr.join()
	arr.toString()    		数组转字符串
	arr.slice(start,end)  		截取数组
	arr.splice(start,howmany,newitems)			数组的增删改
	arr.isArray()		判断一个对象是不是数组	
	arr.concat(otherArr)		连接两个或多个数组
	arr.reverse() 			反转数组


##字符串的常用方法

	String.indexOf()				返回查找该字符正数第一在字符串的索引位置
	String.lastIndexof()			返回该字符最后一个在字符串的索引位置
	String.replace(old,new)			替换字符串
	Sting.cancat(str)				连接字符串
	String.split('参照',length)	   根据参照分割字符串,成为数组,length是数组的长度
	String.slice(start,end)			切割字符串,不含(end)
	String.substring(start,end)		切割字符串,不含(end)
	String.substr(start,length)		切割字符串

	当接收的参数是负数时，slice会将它字符串的长度与对应的负数相加，结果作为参数；
	substr则仅仅是将第一个参数与字符串长度相加后的结果作为第一个参数；
	substring则干脆将负参数都直接转换为0


##排序

####冒泡排序:
	
	
	bubbing (arr) {
        for (let i = 0; i < arr.length; i++) {
          for (let j = 0; j < arr.length - i; j++) {
            if (arr[j] > arr[j + 1]) {
              [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]]
            }
          }
        }
      }	

####选择排序:

	choose (arr) {
        for (let i = 0; i < arr.length; i++) {
          let max = i
          for (let j = i + 1; j < arr.length; j++) {
            if (arr[max] < arr[j]) {
              max = j
            }
          }
          if (max !== i) {
            [arr[max], arr[i]] = [arr[i], arr[max]]
          }
        }
      }


	
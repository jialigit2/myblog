#Scala Must Know

##different from Java

1. 概念上的特点

	1.1 访问修饰符
	
		更严格 private, protected
		
	1.2 数据类型
		
		Unit, Nothing,Null,null
		
	1.3 case class
	
	case class 就是为pattern matching 而生的
	
	
	1.4 trait
	
	
	一般情况下Scala的类只能够继承单一父类，但是如果是 Trait(特征) 的话就可以继承多个，从结果来看就是实现了多重继承。
	
2. 类及伴生对象

什么情况下不用new关键字，cass class, companion object


伴生对像
当单例对象与某个类共享同一个名称时，他被称作是这个类的伴生对象：companion object
3. function and method

Scala 中的函数其实就是继承了 Trait 的类的对象

4. 单例

scala没有static 关键字，object 来提供单例




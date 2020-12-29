Maven 打包
目标：
clean, compile, package, install

几个选项：
-Dmaven.test.skip=true
-DskipTests=true


1. 打包的要求
可执行的jar
	和依赖打包到一起
	依赖和资源文件分开
	zip
给第三方使用的jar, 不包含依赖


2. 插件

		 **几个重要的插件**
		 maven-compiler-plugin
		 maven-dependency-plugin
		 maven-resources-plugin
		 maven-jar-plugin
		 spring-boot-maven-plugin
	 
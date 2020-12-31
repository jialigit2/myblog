Mysql 问题优化：

# 账号管理

## 创建账户：

* 5.8 版本要求西安创建用户然后在授权：
	 
		 CREATE USER 'liujiali'@'%' IDENTIFIED with  mysql_native_password  BY 'Z4lsw@123456#';	
		 Alter user ‘root’ @ ‘localhost’ identified with mysql_native_password by ‘password’; 
		 
		 grant all privileges on *.* to 'liujiali'@'%';
		 GRANT INSERT, UPDATE, DELETE
				ON employees 
				TO bob@localhost;
		 GRANT INSERT 
				ON classicmodels.* 
				TO bob@localhost;
		 flush privileges;


* mysql 权限有：（ privileges）:


		select, insert, update,delete
		CREATE, INSERT, and ALTER
		FILE
		SHOW VIEW
		TRIGGER
		LOCK TABLES
		全部：
		all privileges
		授权/取消 动词
		grant/revoke

# 优化问题：

1.  连接数问题，连接数过多。。。

登录mysql 查看连接数设置，最大连接数，当前正在使用的连接等。。

	show variables like ‘max_connections’; 显示214，默认保留一个连接给管理员，所以最大连接数为215

	show global status like ‘Max_used_connections’; 显示215，当前连接和程序连接

	show processlist 可以看到程序不在运行但是有很多程序的连接依然存在

	show status like ‘Threads%’; Threads_connected | 57 这个数值指的是打开的连接数； Threads_running | 4 这个数值指的是激活的连接数


	set global max_connections=1000 ; 设置最大连接数

systemctl edit mysqld.service
![mysqld.service](../img/mysql/mysqld.service_edit.png)

# problems may encounter
 * Establishing SSL connection without server's identity verification is not recommended. According to MySQL 5.5.45+, 5.6.26+ and 5.7.6+ requirements SSL connection must be established by default if explicit option isn't set. For compliance with existing applications not using SSL the verifyServerCertificate property is set to 'false'. You need either to explicitly disable SSL by setting useSSL=false, or set useSSL=true and provide truststore for server certificate verification.

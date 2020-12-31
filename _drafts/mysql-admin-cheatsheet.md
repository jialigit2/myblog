# Mysql Admin Cheat-Sheet
原生命令：
## dump
	1.
	mysqldump [specified_options] name_of_database [name_of_table ...] > nameOfBackupFile.sql
	
	mysqldump [specified_options] --all-databases > nameOfBackupFile.sql

	2.	
	SELECT * FROM <db> into outfile  '/tmp/mysql_processes.txt';
	
	
	
## Load

	sudo mysql -u root -p --database=call_management_platform_v02< backupOfEducba.sql
	
	mysql -u root -p --database=call_management_platform_v02<backup.sql	
	
	MySQL> LOAD DATA LOCAL INFILE 'book1.csv' INTO table std 
	FIELDS TERMINATED BY ',' 
	ENCLOSED BY '"' 
	LINES TERMINATED BY '\r\n' 
	
	
	
	mysql -u root -p --database=WAIHU< backupOfEducba.sql
	
	
	
## 备份和恢复：
	binlog format: binlog 的模式：必须是行模式才可以恢复，具体办法是将binlog 二进制文件转化为字符模式，然后找到delete语句转化为相应的insert 语句，然后导入到mysql 中，但是row
	
	show global variables like "%binlog_format%";  
	
修改配置文件：/etc/my.cnf

		[mysqld]
		binlog_format="STATEMENT"  
		#binlog_format="ROW"  
		#binlog_format="MIXED" 
转化为字符：
	mysqlbinlog -vv --start-datetime='2020-12-31 09:18:00' 	mysql_bin_log.000094|more;
	
出来结果是文本，进行文本处理，转化为insert 语句。
	
	mysqlbinlog -vv --start-position=192 --stop-position=435 on.000004 |grep ^"###" >/tmp/bin_data


接下来就是处理/tmp/bin_data文本，将里面的delete语句转化为insert语句，可以通过下面的语句实现转化：

	cat /tmp/bin_data | sed -n '/###/p' | sed 's/### //g;s/\/\*.*/,/g;s/DELETE FROM/INSERT INTO/g;s/WHERE/SELECT/g;' |sed -r 's/(@6.*),/\1;/g' | sed 's/@[1-9]=//g' | sed 's/@[1-9][0-9]=//g' >/tmp/person.sql

导入：	

	mysql -h127.0.0.1 -P3306 -uroot -p123 < /tmp/person.sql
	
 参考连接：
	[MySQL的delete误操作的快速恢复方法](https://yq.aliyun.com/articles/664444)
	
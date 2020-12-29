Mysql Admin CheatSheet:
# dump
	1.
	mysqldump [specified_options] name_of_database [name_of_table ...] > nameOfBackupFile.sql
	
	mysqldump [specified_options] --all-databases > nameOfBackupFile.sql

	2.	
	SELECT * FROM <db> into outfile  '/tmp/mysql_processes.txt';
	
	
	
# Load

	sudo mysql -u root -p --database=call_management_platform_v02< backupOfEducba.sql
	
	MySQL> LOAD DATA LOCAL INFILE 'book1.csv' INTO table std 
	FIELDS TERMINATED BY ',' 
	ENCLOSED BY '"' 
	LINES TERMINATED BY '\r\n' 
	
	
	
	mysql -u root -p --database=WAIHU< backupOfEducba.sql
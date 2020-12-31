# lsof cheat-sheet

1. 直接进入系统查看某个进程的句柄
	
		ls -l /proc/pid/fd

2. 句柄数量排序
		
		lsof -n|awk '{print $2}'|uniq -c|sort -nr|head -n 10
3. 修改系统句柄数量（持久）

		/etc/security/limits.conf


4. 修改系统句柄暂时：
		ulimit -a: 查看
		
		ulimit -Hn 65536
		ulimit -Sn 65536
		H: hard
		S: soft
		
5. 排查哪个程序占用句柄数量多

		lsof -p [PID] -r [interval in seconds, 1800 for 30 minutes] > lsof.out
		 
		lsof -p 345031 -r  1800> lsof.out
	r is for repeat mode

6: 查看占用某个端口的进程
	
		lsof -i :port
等价于： 

		netstat -nlp|grep port
		
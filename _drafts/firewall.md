# 查看防火墙状态
service iptables status  
 
# 停止防火墙
service iptables stop  
 
# 启动防火墙
service iptables start  
 
# 重启防火墙
service iptables restart
  
# 永久关闭防火墙
chkconfig iptables off  
 
# 永久关闭后重启
chkconfig iptables on
————————————————
版权声明：本文为CSDN博主「菲宇」的原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/bbwangj/java/article/details/74502967



vim /etc/sysconfig/iptables
# 加入如下代码
-A INPUT -m state --state NEW -m tcp -p tcp --dport 80 -j ACCEPT

service iptables restart


----------------------
systemctl status firewalld
firewall-cmd --state
# 开启
service firewalld start
# 重启
service firewalld restart
# 关闭
service firewalld stop

#查看
firewall-cmd --list-all 

#重启防火墙(修改配置后要重启防火墙)
firewall-cmd --reload

#封禁单个ip
	firewall-cmd --permanent --add-rich-rule="rule family='ipv4' source address='185.53.89.11' reject"  单个IP
	167.172.20.250
	51.89.235.114
	51.81.47.47
	
	
	37.49.226.143
	77.247.110.25
	45.143.220.132
	 
	
	firewall-cmd --permanent --remove-rich-rule="rule family='ipv4' source address='222.90.93.66' reject"
	51.178.92.98
	104.154.233.83
	 
	222.90.93.66   
	
	
	51.81.47.48
	54.36.110.205
	54.81.47.48
	198.199.84.63
	
	
	147.135.71.87
	147.135.46.16
	51.195.5.33
	51.89.21.26
	147.135.46.16
   114.114.114.114


# 查询端口是否开放
firewall-cmd --query-port=8080/tcp
# 开放80端口
firewall-cmd --permanent --add-port=80/tcp
# 移除端口
firewall-cmd --permanent --remove-port=8080/tcp
 
# 参数解释
1、firwall-cmd：是Linux提供的操作firewall的一个工具；
2、--permanent：表示设置为持久；
3、--add-port：标识添加的端口；


封禁 ip

	firewall-cmd --permanent --zone=public --new-ipset=blacklist --type=hash:ip
	
	firewall-cmd --permanent --zone=public --ipset=blacklist --add-entry=222.222.222.222
	
		firewall-cmd --permanent --add-rich-rule="rule family='ipv4' source address='222.222.222.0/24' reject" IP段
	firewall-cmd --permanent --add-rich-rule="rule family=ipv4 source address=192.168.1.2 port port=80  protocol=tcp  accept" 单个IP的某个端口
	
	firewall-cmd --permanent --add-rich-rule="rule family=ipv4 source address=39.104.73.31 port port=8021  protocol=tcp  accept"
	
	4）如下命令可查看当前系统打开的所有端口

firewall-cmd --zone=public --list-ports



nmap  10.0.1.161  -p1-65535



负载均衡主备切换：
管理supervisor:
supervisorctl restart program_name  # 重启某个进程




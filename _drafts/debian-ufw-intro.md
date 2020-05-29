##Debian **ufw** command

1. apt and apt-get 
	 
	> 简单的说就是，apt 是apt-get的优化版本，一般使用apt就可以代替apt-get的大部分常用功能，但二者并非完全相等



2.  ufw 

	>	* ufw 是 **debian** 系统（包括unbutu)的默认防火墙配置工具，目的是简化iptables的配置使用难度
	
	>  * __使用apt安装__： 
	
	
		apt install ufw	
	
	> 
	> 2.1 **常用命令**：
	> 
	> 查看状态 `ufw status verbose`
	> 
	> 开启 `ufw enable`
	> 
	> 关闭 `ufw disable`
	> 
	> 2.2 **默认策略**：
	> 
	>  所有入方向请求禁止，除非例外
	>
	> 具体细节参考：[ufw wiki](https://help.ubuntu.com/community/UFW)
	> 添加一条：
	>> 允许：
	>> 
	>> ufw allow <port>/<可选：协议>
	>> ufw allow 53
	>> ufw allow 53/tcp
	>> 
	>> 禁止
	>> ufw deny <port>/<optional: protocal>
	>> ufw deny 53
	>> ufw deny 53/tcp
	>> 
	>> 删除一条规则
	>> ufw delete deny 53
	
	
	>> 2.3. **高级**  
		
		ufw allow from <target> to <destination> port <port number> proto <protocol name>  
		ufw allow from 192.168.0.0/24 to any port 22 proto 		tcp  
			
		ufw deny from <ip address> to <protocol> port <port number>   
		ufw deny from 192.168.0.1 to any port 22

	>>> 顺序  
		
	>>>**特殊规则往前方，一般规则放后边**
	>>>
	
	sudo ufw status  
	Firewall loaded
	
	To           |              Action | From
	-------------|---------------------|------------------
	22:tcp       |              DENY    |192.168.0.1      |
	22:udp       |              DENY   | 192.168.0.1      |
	22:tcp       |              DENY    |192.168.0.7      |
	22:udp       |              DENY    |192.168.0.7      |
	22:tcp       |              ALLOW  | 192.168.0.0/24   |
   
   
   
  		
   
	

 

	
	
	

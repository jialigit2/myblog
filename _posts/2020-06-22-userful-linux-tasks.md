---
layout: blog  
title:  系统管理必须掌握的linux 命令
tags:  linux
category: IT
author: 刘佳利
---

# 系统管理必须掌握的linux 命令
`sysadmin must-know linux commands`

### 文档管理

1. touch/mv/cp 新建，移动，拷贝
2. chown/chmod修改文件所属，权限
> 权限包括读，写，执行
3. ln -s链接
4. tar -zvf/xvf 压缩，解压缩文档
5. zip/unzip 同上

### 磁盘管理
1. cd ~ 家目录, cd - 上一步所在目录
2. mkdir创建目录
3. du -sh 查看磁盘占用空间
4. df -h  查看系统磁盘占用
5. ls -l 列表显示文件
6. pwd 查看当前路径

### 用户管理

1. adduser/deluser 创建、删除用户
2. addgroup/delgroup 创建，删除用户组
3. passwd 给用户创建密码

### 软件包管理
1. apt/yum/rpm 安装查找安装包
### 网络管理
1. netstat 查看网络端口
2. curl 测试一个服务
3. wget 下载一个资源
4. ifconfig 查看本地ip配置
5. ufw(debian)/firewall-cmd(centos)/iptables 防火墙工具

### 进程管理
1. top/free： 查看系统内存，cpu占用
2. ps afx 可以查看进程父子关系，进程号
3. kill -9 杀死进程
4. nohup process& 后台运行进程
> 运行之后，必须exit 正常退出；不然程序将会中断。

### 系统管理
1. systemctl enable/disable servicename
2. service start/stop/status servicename
3. lsof 查看系统句柄
4. man/help/info 查看帮助信息
	

### 其他工具：
1. 编辑：vi/vim
3. sort
4. uniq
5. tcpdump
> 结合桌面wireshark分析问题
6. less/head/tail/more
7. man/info/help
8. who/whoami
9. which 查看命令执行的文件
10. whereis 
11. find/locate
12. source profile 重新执行profile文件配置
13. find/locate寻找文件
>	find -name / 'expression'
14. grep/pgrep 正则筛选，通常用与管道（|）
15. su/sudo 切换用户/使用超级权限
	
### 配置
1. /etc/passwd 用户
2. ~/.profile 系统默认加载配置文件

### 实例：
1. How to remove many (200 000) files?

	`find -name * | xargs rm -f`
	
2. how to add a new user in linux?

	```
	adduser username
	passwd username
	addgroup  
	deluser
	```

3. how to enable a service to start on boot?

	systemctl enable/disable servicename
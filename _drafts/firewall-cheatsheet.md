# firewall

centos:
systemctl start firewalld 
firewall-cmd --list-all-zones 

[root@localhost ~]#servcie iptables stop                    --临时关闭防火墙
[root@localhost ~]#chkconfig iptables off                    --永久关闭防火墙


查看已经开放的端口：

firewall-cmd --list-ports
开启端口

firewall-cmd --zone=public --add-port=80/tcp --permanent
命令含义：

–zone #作用域

–add-port=80/tcp #添加端口，格式为：端口/通讯协议

–permanent #永久生效，没有此参数重启后失效

重启防火墙

firewall-cmd --reload #重启firewall
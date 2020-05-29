lsof:

查看系统默认的最大文件句柄数，系统默认是1024

# ulimit -n

1024

 

----查看当前进程打开了多少句柄数

# lsof -n|awk '{print $2}'|sort|uniq -c|sort -nr|more

另外通lsof命令也可以查看占用端口（下面查看的是9001端口被哪个进程占用）的进程：

/usr/sbin/lsof-i :9001

 /usr/sbin/lsof-p 21404 命令结果如下
 
 通过cat/proc/pid/fd可以查看线程pid号打开的线程；
 
 ls -1 /proc/${PID}/fd | wc -l
 
 ls -1 /proc/${PID}/fd | wc -l
 
 pfd=lsof -p <pid> |wc -l =>某个进程打开的文件句柄数
=>ptfd=lsof -n|grep <pid> |wc -l =>某个进程及其所有线程打开的文件句柄数
=>pt=ps -Lf <pid> |wc -l =>某个进程下的线程数量
=>ptfd~=pfd*pt
 
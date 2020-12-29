Linux 管道：

拷贝操作：
find . -name "spring*tar-all.tar" | xargs -i cp {} /opt/release/

删除操作：

查看句柄数排序：
lsof -n|awk '{print $2}'|sort|uniq -c|sort -nr|more


统计Apache或nginx日志里访问次数最多的前十个IP或前100都是可以的。

1. 根据访问IP统计UV

	awk '{print $1}' access.log|sort | uniq -c |wc -l

2. 统计访问URL统计PV

	awk '{print $7}' access.log|wc -l

3. 查询访问最频繁的URL

	awk '{print $7}' access.log|sort | uniq -c |sort -nk 1 -r|more

4. 查询访问最频繁的IP

	awk '{print $1}' access.log|sort | uniq -c |sort -nk 1 -r|more

5. .根据时间段统计查看日志

	cat access.log| sed -n '/14\/Mar\/2015:21/,/14\/Mar\/2015:22/p'|more


 

awk '{ print $1}'：取数据的低1域（第1列）

sort：对IP部分进行排序。

uniq -c：打印每一重复行出现的次数。（并去掉重复行）

sort -nr -k1：按照重复行出现的次序倒序排列,-k1以第一列为标准排序。

head -n 10：取排在前5位的IP 。

您这边找到您的访问日志进行统计就可以了。


# 文件句柄：

ls -l /proc/pid/fd
/etc/security/limits.conf

ulimit -Sn 65536

ulimit -Hn 65536

output the lsof overtime

lsof -p [PID] -r [interval in seconds, 1800 for 30 minutes] > lsof.out
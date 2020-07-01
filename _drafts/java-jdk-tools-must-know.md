

1. jstat 查看堆内存

	jstat -gc垃圾回收统计
	监控运行状态，类装载，内存，垃圾收集
	定位虚拟机性能问题
	
2. jmap &&jhat
	jmap -histo \<vmid>
	堆栈信息，查看java对使用情况
	java对使用情况的内存镜像
	内存泄漏

3. jstack 线程快照

	堆栈跟踪工具
	
	当前时刻的线程快照，定位线程长时间出现停顿的原因
	
4. eclipse mat工具
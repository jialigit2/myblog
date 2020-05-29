#<center>Java 内存问题定位相关知识</center>

## 内存堆溢出 Heap OutOfMemory

## 栈溢出 StackOverFlow
# 线程快照

对象数量，引用关系
# Java内存模型，垃圾收集

> -Xmn/-Xms/-Xmx 参数
> 堆栈，类， 对象，常量
> 对象生命周期，虚拟机垃圾回收机制
> Shallow Heap/retained Heap
> Eden, Young, Old
> 
> - 内存快照存取jmap
> jmap -dump:file= \<path:ie:heap1/heap.hprof\> \<pid\> 
> 
> >**ie: jmap -dump:file=heap.hprof 13085**
> 
> 
> 
> 
> 
> 

## 分析工具
- jdk自带分析工具 jhat heap.hprof 是一个http服务，打开Html 页面
- Eclipse Mat独立的工具，分析潜在内存泄漏问题

## Instrumentation API

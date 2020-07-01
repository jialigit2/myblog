#java-must-know

**Java must know for java developers**

> 关于Java平台   

1. GC，多线程和内存模型

垃圾回收的设计是为了解除程序员需要手动管理内存空间的麻烦，减少出错，增大了编程的效率。

奇怪的是现在又有很多人需要你知道垃圾回收的原理呢？



引用计数法
可达性分析

2. 内存模型 
运行时
编译器
多处理器

堆： 给程序员的对象的用的内存池

栈：LIFO, 虚拟机栈，创建线程时创建，线程私有

引用和对象：
引用在栈，对象在堆。

3. 重排序 and 多线程


2. type and class
java中的基本的数据类型有：

byte,int,double,char,boolean


 传值和传址：pass-by-value vs pass-by-address
 
 

##4. Java 的生态 

4.1 Web 开发 
Java最主要是作为web应用的后端语言，拥有丰富的生态和工具

4.1.1 Spring Framework,Spring Boot

Spring Core: 
Spring容器:Bean Factory
依赖注入(dependency injection)/控制反转(control inversion)

把组装对象的任务交给容器来完成。


> 数据库的事务

ANSI/ISO SQL定义的标准隔离级别有四种，从高到底依次为：可序列化(Serializable)、可重复读(Repeatable reads)、提交读(Read committed)、未提交读(Read uncommitted)。
 - 事务的隔离级别
 脏读，幻读，不可重复读
 
 - 
 - 

> Spring的事务管理

编程式事务，声明式事务

事务属性的方面：
传播行为
隔离级别
回滚规则
事务超时
是否只读


事务传播行为

解决业务层方法相互调用的事务问题

方法在现有事务中执行还是开启新的事务

###4.1.2 JDBC, 连接池

C3P0,DRUID

###4.1.3 MVC

web应用设计模式


###4.1.4 ORM框架 

Mybatis,Hibernate,JPA,JdbcTemplate
对象关系映射
Mybatis:sql 映射框架
Hibernate:ORM 框架

##SQL 5.1 

basics 

** basic data type基本数据类型

int char varchar text date time datetime float blob json 

** create/alter/drop database, table add column rename table

** add constraint 增加约束

add primary key auto-increment add foreign key() reference () add check unique not null ** select from

** join/left join/right join链接

**union/union all联合

** subquery子查询

** where clause and,or,not,in ** aggregation group by ** function函数

** delete from

** view视图

** temperary table临时表

5.2 数据库管理 

mysqladmin mysqldump 

grant priviledges on <..> to <..>

导出到外部文件
select <...> into outfile create table from select <...>

5.3 SQL 优化 

where , order by涉及的列上建立索引

避免全表扫描

where中避免 使用 ！=, 因为不会使用索引


index建立索引 

** unique,primary fulltext explain limit offset,count limit count

分布式计算 

Spring Cloud基于Spring Boot
fast-failover 负载均衡 横向扩展 监控，熔断

API 网关 注册 中心 Mesage Broker

函数式编程，Scala, 流式计算API Java 8
什么是scala,有哪些特性？lamda 表达式，高阶函数 8. 大数据 hdfs,mapreduce hadoop, spark storm,flume hbase,hive

9 软件架构
9.1 分布式系统CAP 理论

9.2 分布式系统
计算，存储

大任务分派到多个计算机单元，然后再汇总

避免单点故障

在分布式系统中保证数据的一致性和可用性和可用性是个问题


9.2 事务
> ACID
Atomic
Consistent
Isolated


> 柔性事务

异步确保型、补偿型、最大努力通知型
刚性事务---传统数据库
> 基本可用，最终一致


两阶段提交协议，三阶段提交协议

JDBC 事务，JTA 事务

分布式一致性

一个基于CAP的最终一致性理论BASE理论是目前解决分布式问题比较靠谱的。


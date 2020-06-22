## Java concurency must know

1. 并发，并行
2. 线程，进程
3. 同步 vs 异步
4. 线程，父线程，子线程，守护线程(daemon)
5. 线程通信
Thread, Runnable, Callable


java 并发包:java.util.concurent
6. 线程池ThreadPool
7. ExecutorService，ThreadPoolExecutor, Executors, Single
```		Executors.newScheduledThreadPool(1);
		Executors.newFixedThreadPool(2);
		Executors.newCachedThreadPool();
		Executors.newSingleThreadExecutor();
		Executors.newWorkStealingPool();
```

ScheduledThreadPoolExecutor


8. Lock/Reentrant Lock
9. optimistic Lock vs persimistic Lock
10. synchronized vs Lock
11. ReadWriteLock
12. ReentrantReadWriteLock
12. 死锁， 活锁
13. 通信机制： Latch, Semephore, CyclicBarrier, Condition
```
	CountDownLatch
	


```
14. Future, 
15. CompletableFuture
java 线程安全类
14. ConcurrentHashMap
15. BlockingQueue,
16. BlockingDeque
17. PriorityBlockingQueue
17. ConcurrentLinkedQueue,ConcurrentLinkedDeque
17. ArrayBlockingQueue, LinkingBlockingQueue
18. CopyOnWriteArrayList
设计模式

14. 生产者消费者模式(producer)
15. Reactor模式
16. 
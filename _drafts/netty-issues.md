###  Netty must-know 


1. 什么是异步和事件驱动模型？

2. 什么是IO多路复用？

3. netty中的线程模型是怎样的？

4. 什么是面向流的链接？
5. Channel和Socket的区别？
6. Reactor设计模型
7. 关注点分离在Netty中的体现？
8. EventLoop 和 EventLoopGroup?
9. BootStrap vs ServerBootStrap
10. ChannelHandler vs ChannelPipeline
11. ChannelFuture vs Future
12. Inbound vs OutBound
13. Selector vs Multiplexer
14. Callback vs asynchroneous
15. What is Event
16. What is ByteBuf
17. What is ReferenceCount
18. What is encode and decode?
JDK NIO
Vs
Netty NIO



netty的基本API：
NonBlocking IO
IO-bound
CPU-bound

corotine/reactor deisn pattern

ByteBuf
ByteBufHolder
ByteBufAllocator

Channel
ChannelPipeline
ChannelHandler
ChannelHandlerContext

InBound/OutBound
Adaptor
hook in state changes
fireXXX

Byte2Message
Message2Byte


Encode/Decode


Reactor 
EventLoop/Event
Acceptor Thread
Worker Thread


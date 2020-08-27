|收集器名称 | &nbsp;&nbsp;区域&nbsp;&nbsp; | 说明|
|:------|:-------|:------|
|Serial | 新生代 |	单线程，GC时必须停止其它线程直到收集结束；JVM运行在client模式下新生代的默认收集器，简单有效；采用复制算法|
|ParNew |	新生代 |	Serial收集的多线程版，保留Serial的参数控制，算法等，暂停所有用户线程，采用复制算法；JVM运行在server的首先的新生代收集器；只有它能和CMS配合工作|
|Parallel Scavenge | 新生代 | 采用复制算法，并行的多线程收集器，与ParNew不同的是，关注点不是停顿时间，而是可控制的吞吐量，即运行用户代码的时间/(运行用户代码的时间+垃圾收集的时间)。可设置最大GC时间和吞吐量大小等参数，也可以让JVM自适应调整策略|
|G1 |	新生代/老年代 |	收集器最前沿版本，JDK 1.7，代替CMS的新产品|
|CMS | 新生代 | Concurrent Mark Sweep，已获取最短回收停顿为目标，大部分的互联网站及服务端采用的方式，标记-清除算法|
|Serial Old(MSC) | 老年代 | Serial的老年版，单线程收集器，采用标记-整理算法，主要是client模式的JVM使用|
|Parallel Old |	老年代 |	Parallel Scavenge的老年版，多线程，标记整理算法|
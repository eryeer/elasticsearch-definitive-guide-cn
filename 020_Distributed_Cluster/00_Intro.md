## 体验集群

>### 补充章节

>正如之前提及的，这是关于Elasticsearch分布式操作的一些补充章节的第一部分。这个章节我们解释一些通用的术语，例如**集群(cluster)**、**节点(node)**和**分片(shard)**，Elasticsearch的扩展机制，以及它如何处理硬件故障。

>尽管这章不是必读的——你可以长时间使用Elasticsearch而不必担心分片、复制和故障转移——但是它会帮助你理解Elasticsearch内部的工作流程，你可以先跳过这章，以后再来查阅。

Elasticsearch用于构建高可用和可扩展的系统。扩展的方式可以是购买更好的服务器(**纵向扩展(vertical scale or scaling up)**)或者购买更多的服务器（**横向扩展(horizontal scale or scaling out)**）。

Elasticsearch能从更强大的硬件中获得更好的性能，但是纵向扩展也有一定的局限性。真正的扩展应该是横向的，它通过增加节点来传播负载和增加可靠性。

对于大多数数据库而言，横向扩展意味着你的程序将做非常大的改动来利用这些新添加的设备。对比来说，Elasticsearch天生是分布式的：它知道如何管理节点来提供高扩展和高可用。这意味着你的程序不需要关心这些。

在这章我们将探索如何创建你的**集群(cluster)**、**节点(node)**和**分片(shards)**来按照你的需求扩展，并保证在硬件故障后数依旧安全。
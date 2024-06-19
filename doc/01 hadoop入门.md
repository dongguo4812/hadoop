# Hadoop概述

## Hadoop是什么

1）Hadoop是一个由Apache基金会所开发的分布式系统基础架构。

2）主要解决，海量数据的存储和海量数据的分析计算问题。

3）广义上来说，Hadoop通常是指一个更广泛的概念——Hadoop生态圈。

![image-20240619111743724](https://gitee.com/dongguo4812_admin/image/raw/master/image/202406191400473.png)

## Hadoop三大发行版本（了解）

Hadoop三大发行版本：Apache、Cloudera、Hortonworks。

Apache版本最原始（最基础）的版本，对于入门学习最好。2006诞生

Cloudera内部集成了很多大数据框架，对应产品CDH。2008诞生

Hortonworks文档较好，对应产品HDP。2011诞生 ，2018年Hortonworks已经被Cloudera公司收购，推出新的品牌CDP。

### 1）Apache Hadoop

官网地址：http://hadoop.apache.org
下载地址：https://hadoop.apache.org/releases.html

### 2）Cloudera Hadop

官网地址：https://www.cloudera.com/downloads/cdh
下载地址：https://docs.cloudera.com/documentation/enterprise/6/release-notes/topics/rg_cdh_6_download.html

### 3）Hortonworks Hadoop

网地址：https://hortonworks.com/products/data-center/hdp/
下载地址：https://hortonworks.com/downloads/#data-platform

## Hadoop优势（4高）

1）高可靠性：Hadoop底层维护多个数据副本，所以即使Hadoop某个计算元素或存储出现故障，也不会导致数据的丢失。

![image-20240619112242322](https://gitee.com/dongguo4812_admin/image/raw/master/image/202406191400225.png)

2）高扩展性：在集群间分配任务数据，可方便的扩展数以千计的节点。

![image-20240619112303281](https://gitee.com/dongguo4812_admin/image/raw/master/image/202406191400203.png)

3）高效性：在MapReduce的思想下，Hadoop是并行工作的，以加快任务处理速度。

![image-20240619112353307](https://gitee.com/dongguo4812_admin/image/raw/master/image/202406191400511.png)

4）高容错性：能够自动将失败的任务重新分配。

![image-20240619112410453](https://gitee.com/dongguo4812_admin/image/raw/master/image/202406191401012.png)

## Hadoop组成（面试重点）

在Hadoop1.x时代，Hadoop中的MapReduce同时处理业务逻辑运算和资源的调度，耦合性较大。
在Hadoop2.x时代，增加了Yarn。Yarn只负责资源的调度，MapReduce只负责运算。
Hadoop3.x在组成上没有变化。

![image-20240619114042779](https://gitee.com/dongguo4812_admin/image/raw/master/image/202406191401273.png)

### HDFS架构概述

Hadoop Distributed File System，简称HDFS，是一个分布式文件系统。

1）NameNode（nn）：存储文件的元数据，如文件名，文件目录结构，文件属性（生成时间、副本数、文件权限），以及每个文件的块列表和块所在的DataNode等。

2）DataNode(dn)：在本地文件系统存储文件块数据，以及块数据的校验和。

3）SecondaryNameNode(2nn)：每隔一段时间对NameNode元数据备份。

![在这里插入图片描述](https://gitee.com/dongguo4812_admin/image/raw/master/image/202406191401637.png)

### YARN架构概述

Yet Another Resource Negotiator简称YARN，另一种资源协调者，是Hadoop的资源管理器。

![img](https://gitee.com/dongguo4812_admin/image/raw/master/image/202406191401838.jpeg)

1）ResourceManager（RM）：整个集群资源（内存、CPU等）的老大
2）NodeManager（NM）：单个节点服务器资源老大
3）ApplicationMaster（AM）：单个任务运行的老大
4）Container：容器，相当一台独立的服务器，里面封装了任务运行所需要的资源，如内存、CPU、磁盘、网络等。

### MapReduce架构概述

MapReduce将计算过程分为两个阶段：Map和Reduce

1）Map阶段并行处理输入数据

2）Reduce阶段对Map结果进行汇总

![img](https://gitee.com/dongguo4812_admin/image/raw/master/image/202406191401003.jpeg)

### HDFS、YARN、MapReduce三者关系

![img](https://gitee.com/dongguo4812_admin/image/raw/master/image/202406191401011.jpeg)

## 大数据技术生态体系
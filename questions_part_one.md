# 调度队列和优化
1. Golang 实现无重复元素的队列

2. Golang 实现固定Size的循环队列

3. 模拟货运运输和优化
假设： 有N个货物，每个货物有三个属性：
货物ID、货物装上车耗费的时间、货物装车后价值。
假设N个货物同时到达站点等待装车,装车操作有序执行<br>
作答要求：<br>
(1)模拟N个货物的单个货物的耗费时间、货物价值 <br>
(2)输出：计算N个货物总排队时间 <br>
总排队执行时间：<br>
    定义第n个货物排队+执行耗时 time(n),n=0,time(0)=0 <br>
    定义第n个货物装车时间 load(n)= 随机值 <br>
    第n个货物排队执行时间：time(n)= time(n-1)+load(n) <br>
(3)编程语言：java、golang、c、c++ 任意一种<br>

4. 基于上面试题3，假设货物之间装载没有依赖关系，谁先谁后都是可以的<br>
假设货车体积有限，如何优化，使得使得等待时间最小、货物价值最大？<br>
编程语言：java、golang、c、c++ 任意一种

5. 模拟公平调度算法实现
例如：Linux Completely Fair scheduler (CFS) 或者 hadoop Fair Scheduler模拟实现
参考链接
<pre><code>
https://en.wikipedia.org/wiki/Completely_Fair_Scheduler
https://github.com/kanaka/rbt_cfs
http://www.dreamincode.net/forums/topic/147939-fair-scheduling-in-java/
http://dongxicheng.org/mapreduce/hadoop-fair-scheduler/
https://github.com/sakeven/RbTree
</code></pre>

6. 模拟Goroutine调度器
Scalable Go Scheduler Design <br>
Go Preemptive Scheduler Design <br>
NUMA‐aware scheduler for Go <br>

7. 基于Golang 模拟 定时任务框架
要求：支持超时控制、支持主动停止任务、支持任务调度周期的改变

# 调度稳定性方面
1. Golang实现
Pod打散的一种算法
需求描述：有一堆候选服务器列表，每个服务器随机分配一个得分，<br>
服务器同时属于一个pod并且只属于唯一一个pod <br>
算法输出：进行按得分排序，同时兼顾按pod打散的 topN 输出 <br>
举例：10个结点，结点如下，
<pre><code>
{nc:a,score:1.0,pod:1}
{nc:b,score:1.0,pod:2}
{nc:c,score:4.0,pod:3}
{nc:d,score:3.0,pod:2}
{nc:e,score:4.0,pod:5}
{nc:f,score:2.0,pod:4}
{nc:g,score:2.0,pod:3}
{nc:h,score:2.0,pod:1}
{nc:i,score:4.0,pod:3}
{nc:j,score:3.0,pod:2}
 
top5：输出如下：
{nc:e,score:4.0,pod:5}
{nc:c,score:4.0,pod:3}
{nc:b,score:3.0,pod:2}
{nc:a,score:2.0,pod:1}
{nc:e,score:2.0,pod:4}
 
top4：输出如下：
{nc:e,score:4.0,pod:5}
{nc:c,score:4.0,pod:3}
{nc:b,score:3.0,pod:2}
{nc:a,score:2.0,pod:1}
或者 任意一个输出都算有效
{nc:e,score:4.0,pod:5}
{nc:c,score:4.0,pod:3}
{nc:b,score:3.0,pod:2}
{nc:e,score:2.0,pod:4}
 
top6：输出如下
{nc:e,score:4.0,pod:5}
{nc:c,score:4.0,pod:3}
{nc:b,score:3.0,pod:2}
{nc:a,score:2.0,pod:1}
{nc:e,score:2.0,pod:4}
{nc:i,score:4.0,pod:3}
</code></pre>

# 分布式一致性方面
1. Java或者Golang实现
一致性hash算法

2. 模拟raft协议中leader 选举。
通俗说N个node，只要一半以及以上node 获得投票 就成为leader，选举结束

3. Golang实现LRUCache

4. Golang实现 任务中断或者宕机可恢复的生产者、消费者框架

# 数据分析和算法
1. N个时序结点，每个结点包括timestamp、value <br>
要求拟合 时序趋势

2. 有N个数据结点，数值区间0 到 100 <br>
要求给出 N个结点的 99分位值

3. 有N个数据结点，数值区间0 到 100
要求 给出一个数值，给出这个数值的分组值

4. 组合关系挖掘
给定N个Node，每个Node上0到M 个 Container <br>
同时，Node分配一个cpu值，每个Container一个cpu值 <br>
Node 和Container的 cpu 值区间0到60 <br>
Node cpu = 上面所有Container cpu 和 每个Container 包括一个 id，name，cpu值 <br>
并且Container id相同的，其cpu值也相同 <br>
<br>要求：<br>
从N个Node和每个Node上面的Container数据中 <br>
挖掘有效组合关系模型，也就 那些Container在一起最佳 <br>
最佳的标准：Node cpu值最大或者最小 <br>

5. 有N个Node，M个Container，每个Node 包括CPU、mem、disk值 <br>
每个Container也包括CPU、mem、disk值 <br>
有Q个工单，每个工单对应一种Container和数量 <br>
要求：<br>
如何将Q个工单资源编排进N个Node，使得N个Node的分配率最好 <br>

# 开源源码
1. etcd源码
2. kubelet源码
3. yarn 源码
4. messos源码
5. CloudSim源码
6. Google-cluster-sim 源码
7. Golang源码
8. Docker 源码
9. Pouch 源码





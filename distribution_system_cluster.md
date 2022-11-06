# 【分布式系统集群】相关的命名

## 集群节点

| 开源软件名称 | 英文名 | 描述 | 参考来源 |
| --- | --- | --- | --- |
| redis | Cluster Node  | 集群节点 | [clusterNode](https://github.com/redis/redis/blob/7.0.5/src/cluster.h#L115) |
| etcd | Member | 集群成员 | [type Member struct](https://github.com/etcd-io/etcd/blob/v3.5.5/client/v2/members.go#L34)<br/>[How to Add and Remove Members](https://etcd.io/docs/v3.5/tutorials/how-to-deal-with-membership/) |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

## 集群主从节点
| 开源软件名称 | 英文名 | 描述 | 参考来源 |
| --- | --- | --- | --- |
| redis | Master / Slave  | 主/从节点 | [CLUSTER_NODE_MASTER / CLUSTER_NODE_SLAVE](https://github.com/redis/redis/blob/7.0.5/src/cluster.h#L47) |
| etcd | Leader / Follower | 领导者 / 追随者 | [type Member struct](https://github.com/etcd-io/etcd/blob/v3.5.5/client/v2/members.go#L34)<br/>[How to Add and Remove Members](https://etcd.io/docs/v3.5/tutorials/how-to-deal-with-membership/) |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

## 添加节点

| 开源软件名称 | 英文名 | 描述 | 参考来源 |
| --- | --- | --- | --- |
| redis | CLUSTER MEET | 添加节点 | [connect different Redis nodes with cluster support enabled, into a working cluster](https://redis.io/commands/cluster-meet) |
| etcd | MemberAdd | 集群成员 | [adds a member into the cluster](https://etcd.io/docs/v3.5/dev-guide/api_reference_v3) |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

## 删除节点

| 开源软件名称 | 英文名 | 描述 | 参考来源 |
| --- | --- | --- | --- |
| redis | CLUSTER FORGET | 删除节点 | [remove a node, specified via its node ID](https://redis.io/commands/cluster-forget) |
| etcd | MemberRemove | 集群成员 | [removes an existing member from the cluster](https://etcd.io/docs/v3.5/dev-guide/api_reference_v3) |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

## 数据分片

> 将数据分散在不同的机器上，以解决单点计算和存储的瓶颈问题。

| 开源软件名称 | 英文名 | 描述 | 参考来源 |
| --- | --- | --- | --- |
| cassandra | Partitions | 分片 | [Cassandra partitions data over the storage nodes using a variant of consistent hashing for data distribution](https://cassandra.apache.org/doc/4.1/cassandra/data_modeling/intro.html#partitions) |
| redis | Key distribution model | 集群成员 | [The cluster's key space is split into 16384 slots, effectively setting an upper limit for the cluster size of 16384 master nodes](https://redis.io/docs/reference/cluster-spec/#key-distribution-model) |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

- [一致性哈希算法（consistent hashing）](https://zhuanlan.zhihu.com/p/129049724)
- [Redis分片机制](https://zhuanlan.zhihu.com/p/367227866)
- [Cassandra内部原理和底层实现 经典的gossip通讯协议](https://www.bilibili.com/video/BV1Ys411g7ij)

## 数据压缩（Compaction）

> 同一个 Key 的值可能会不断的变化，为了快速写入，以 AppendOnly 的方式会记录同一个 Key 的所有历史变更值，为了节省空间与加速计算，可以将同一个 Key 的所有历史值进行压缩，删除老值，仅保留最新的值。

| 开源软件名称 | 英文名 | 描述 | 参考来源 |
| --- | --- | --- | --- |
| cassandra | Compaction | 数据压缩 | [Compaction](https://cassandra.apache.org/doc/4.1/cassandra/operating/compaction/index.html) |
| kakfa | Log Compaction | 日志压缩 | [Log Compaction](https://kafka.apache.org/32/documentation.html#compaction) |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
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

## 集群节点列表查看

| 开源软件名称 | 查看命令 | 描述 | 参考来源 |
| --- | --- | --- | --- |
| k8s | kubectl get nodes | 查看k8s集群节点列表 | [Viewing Pods and Nodes](https://kubernetes.io/docs/tutorials/kubernetes-basics/explore/explore-intro/) |
| docker swarm | docker node ls | 查看docker swarm节点列表 | [docker node ls](https://docs.docker.com/engine/reference/commandline/node_ls/) |
| redis sentinel | cluster nodes | 查看redis集群节点列表 | [CLUSTER NODES](https://redis.io/commands/cluster-nodes/) |
| redis cluster | sentinel master/replicas/sentinels mymaster | 查看redis sentinel主/从/哨兵节点列表 | [sentinel master mymaster](https://redis.io/docs/management/sentinel/#asking-sentinel-about-the-state-of-a-master) |
| cassandra | describe cluster | 查看cassandra集群名称/分片器等 | [DESCRIBE CLUSTER](https://cassandra.apache.org/doc/4.1/cassandra/tools/cqlsh.html#describe) |
| cassandra | nodetool status | 查看cassandra集群节点列表等信息 | [Cluster Status](https://cassandra.apache.org/doc/4.1/cassandra/troubleshooting/use_nodetool.html#nodetool-status) |
| kafka | ./zookeeper-shell.sh localhost:2181 ls /brokers/ids | 查看kafka集群的broker列表 | [How to list all available Kafka brokers in a cluster?](https://stackoverflow.com/questions/40146921/how-to-list-all-available-kafka-brokers-in-a-cluster) |
| rocketmq | ./mqadmin clusterList -n namesrv:9876 | 查看rocketmq集群的broker列表 | [Admin Tool](https://rocketmq.apache.org/docs/4.x/deployment/16admintool#%E9%9B%86%E7%BE%A4%E7%9B%B8%E5%85%B3) |
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
- [Cassandra一致性哈希分片](https://cassandra.apache.org/doc/4.1/cassandra/architecture/dynamo.html#consistent-hashing-using-a-token-ring)

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

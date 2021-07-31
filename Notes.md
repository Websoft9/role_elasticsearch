elasticsearch开启远程访问
### Remote
修改elasticsearch的主配置文件elasticsearch.yml

找到Network区域

为es设置ip绑定，默认是127.0.0.1，也就是默认只能通过127.0.0.1 或者localhost才能访问

将 network.host: 192.168.0.1 修改为 network.host: 0.0.0.0 


```
# Set the bind address to a specific IP (IPv4 or IPv6):
#
network.host: 0.0.0.0
#
# Set a custom port for HTTP:
#
http.port: 9200
#
# For more information, consult the network module documentation.
```

es7.x之后版本增加了Discovery区域

开启远程需要初始化一个新的集群时需要 cluster.initial_master_nodes 配置来选举master

修改#cluster.initial_master_nodes: ["node-1", "node-2"] 为 cluster.initial_master_nodes: ["你的节点名字"]

```
# --------------------------------- Discovery ----------------------------------
#
# Pass an initial list of hosts to perform discovery when this node is started:
# The default list of hosts is ["127.0.0.1", "[::1]"]
#
#es7.x 之后新增的配置，节点发现
#discovery.seed_hosts: ["host1", "host2"]
#
# Bootstrap the cluster using an initial set of master-eligible nodes:
#
#es7.x 之后新增的配置，初始化一个新的集群时需要此配置来选举master
#cluster.initial_master_nodes: ["node-1", "node-2"]
#
# For more information, consult the discovery and cluster formation module documentation.
```
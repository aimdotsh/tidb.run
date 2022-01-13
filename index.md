



# Oracle Cloud ARM 单机服务器安装 tidb 集群

申请的 Oracle Cloud ARM 服务器一直闲置，发现 tidb 支持 ARM 架构，正好现在在准备 PCTP 的考试，就由他来进行模拟测试，当时准备 PCTA 的时候是从阿里云买了 7 台服务器搭建了一套集群，Oracle Cloud ARM 



```
[root@instance-20211219-1910 ~]#  tiup cluster deploy  tidbcluster  5.3 ./topo.yaml --user root -p
Starting component `cluster`: /root/.tiup/components/cluster/v1.8.2/tiup-cluster deploy tidbcluster 5.3 ./topo.yaml --user root -p
Input SSH password: 

+ Detect CPU Arch
  - Detecting node 10.0.0.145 ... Done
Please confirm your topology:
Cluster type:    tidb
Cluster name:    tidbcluster
Cluster version: v5.3
Role        Host        Ports                            OS/Arch        Directories
----        ----        -----                            -------        -----------
pd          10.0.0.145  2379/2380                        linux/aarch64  /tidb-deploy/pd-2379,/tidb-data/pd-2379
tikv        10.0.0.145  20160/20180                      linux/aarch64  /tidb-deploy/tikv-20160,/tidb-data/tikv-20160
tikv        10.0.0.145  20161/20181                      linux/aarch64  /tidb-deploy/tikv-20161,/tidb-data/tikv-20161
tikv        10.0.0.145  20162/20182                      linux/aarch64  /tidb-deploy/tikv-20162,/tidb-data/tikv-20162
tidb        10.0.0.145  4000/10080                       linux/aarch64  /tidb-deploy/tidb-4000
tiflash     10.0.0.145  9000/8123/3930/20170/20292/8234  linux/aarch64  /tidb-deploy/tiflash-9000,/tidb-data/tiflash-9000
prometheus  10.0.0.145  9090                             linux/aarch64  /tidb-deploy/prometheus-9090,/tidb-data/prometheus-9090
grafana     10.0.0.145  3000                             linux/aarch64  /tidb-deploy/grafana-3000
Attention:
    1. If the topology is not what you expected, check your yaml file.
    2. Please confirm there is no port/directory conflicts in same host.
Do you want to continue? [y/N]: (default=N) y
+ Generate SSH keys ... Done
+ Download TiDB components
  - Download pd:v5.3 (linux/arm64) ... Error
  - Download tikv:v5.3 (linux/arm64) ... Error
  - Download tidb:v5.3 (linux/arm64) ... Error
  - Download tiflash:v5.3 (linux/arm64) ... Error
  - Download prometheus:v5.3 (linux/arm64) ... Error
  - Download grafana:v5.3 (linux/arm64) ... Error
  - Download node_exporter: (linux/arm64) ... Done
  - Download blackbox_exporter: (linux/arm64) ... Done

Error: version v5.3 on linux/arm64 for component tikv not found: unknown version

Verbose debug logs has been written to /root/.tiup/logs/tiup-cluster-debug-2022-01-12-08-17-10.log.
Error: run `/root/.tiup/components/cluster/v1.8.2/tiup-cluster` (wd:/root/.tiup/data/SuHxUix) failed: exit status 1
[root@instance-20211219-1910 ~]# 
```



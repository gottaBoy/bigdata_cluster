# vagrant_bigdata_cluster (maxwell环境)

https://github.com/endymecy/spark-ml-source-analysis

https://github.com/gottaBoy/SparkInternals

https://toscode.gitee.com/koopo/spark-spring

https://github.com/gottaBoy/learning-hadoop

https://github.com/gottaBoy/CoolplaySpark

https://github.com/gottaBoy/BigData-Interview


https://github.com/gottaBoy/spark-streaming-action

## 一、基本介绍

本集群创建的组件如下表所示。

|   组件    | hdp101         | hdp102         | hdp103         |
| :-------: | -------------- | -------------- | -------------- |
|    OS     | centos7.6      | centos7.6      | centos7.6      |
|    JDK    | jdk1.8         | jdk1.8         | jdk1.8         |
| Zookeeper | QuorumPeerMain | QuorumPeerMain | QuorumPeerMain |
|   Kafka   | kafka          | Kafka          | Kafka          |
|   MySQL   | NA             | NA             | MySQL Server   |
|  Maxwell  | Maxwell        | NA             | NA             |

## 二、基本硬件准备

1. 集群默认启动三个节点，每个节点的默认内存是2G，所以你的机器至少需要6G
2. 我的测试环境：Vagrant 2.2.14， Virtualbox 6.0.14

## 三、安装集群环境

1. [下载和安装VirtualBOX](https://www.virtualbox.org/wiki/Downloads)

2. [下载和安装Vagrant](http://www.vagrantup.com/downloads.html)

3. 克隆本项目到本地，并cd到项目所在目录

   ```
   git clone https://github.com/yiluohan1234/vagrant_bigdata_cluster
   cd vagrant_bigdata_cluster
   git checkout env_maxwell
   ```

4. 执行`vagrant up` 创建虚拟机

5. 可以通过执行 `vagrant ssh` 登录到你创建的虚拟机，或通过SecureCRT等工具进行登录

6. 如果你想要删除虚拟机，可以通过执行`vagrant destroy` 来实现

## 四、自定义集群环境配置

基本目录结构

```
resources
scripts
.gitignore
README.md
VagrantFile
```

你可以通过修改`VagrantFile`、`scripts/common.sh`文件和`resources/组件名称`目录下各个组件的配置文件文件来实现自定义集群。

1. `VagrantFile`
   这个文件可以设置虚拟机的的版本、个数、名称、主机名、IP、内存、CPU等，根据自己需要更改即可。

2. `scripts/common.sh`
   这个文件可以设置各个组件的版本。

   > 注意：部分组件需要同步更改`XXX_VERSION`和`XXX_MIRROR_DOWNLOAD`，保证能下载到组件版本。


## 五、集群安装完毕后相关组件初始化及启动

### 1、ssh免登陆

在每台机器上执行以下

```
setssh
```

### 2、启动zookeeper和kafka

```
mv maxwell-1.29.2 maxwell
chown -R vagrant:hadoop /opt/module
bigstart zookeeper start
bigstart kafka start


bigstart dfs start

```

### 启动链接
- [hadoop](http://hdp101:9870/)
- [hbase](http://hdp101:16010/)
- [flink](http://hdp101:8381/)
- [yarn](http://hdp102:8088/)
- [mrhistory](http://hdp102:19888/)

### Hbase shell
HMaster HRegionServer

### 本地链接问题
https://blog.csdn.net/whs0329/article/details/121878162

https://github.com/steveloughran/winutils
HADOOP_HOME=
hadoop.dll文件放到 C:/windows/system32

### 3、启动maxwell

```
bigstart maxwell start
```

###
Hadoop分布式集群的搭建
https://blog.csdn.net/theVicTory/article/details/124095680

网关
快速理解VirtualBox的四种网络连接方式
https://blog.csdn.net/Alezan/article/details/124070178
虚拟机联网问题总结-VMWare桥接、NAT模式、仅主机模式解释与配置
https://blog.51cto.com/yangshufan/1959448
http://www.javashuo.com/article/p-owhlwymx-vz.html

https://zhuanlan.zhihu.com/p/403513377

### netplan
https://zhuanlan.zhihu.com/p/458822186

### kafka
https://blog.csdn.net/u011110301/article/details/119445017

https://github.com/Thpffcj/BigData-Getting-Started
https://github.com/gingerredjade/flink-userportrait-main
https://github.com/will-che/flink-recommandSystem-demo
https://github.com/zlt2000/microservices-platform
https://github.com/authorwlh/alldata
https://github.com/wangzhiwubigdata/God-Of-BigData

激活idea
- [激活idea](https://tobebetterjavaer.com/nice-article/itmind/ideapxideajhideayjjhmideazxjhzcmpjjcyjjhqcyx.html)
- [激活链接2](https://segmentfault.com/a/1190000041984899)
- [激活工具](https://www.lanzoul.com/ikV6Szw3mre)


### 
https://kubernetes.feisky.xyz/
https://www.yuque.com/ivescode/k8s/pskdlv
https://www.yuque.com/leifengyang/oncloud/ctiwgo


### Apache Doris + Apache Flink + Apache DolphinScheduler + Dinky 构建开源数据平台
http://www.dlink.top/
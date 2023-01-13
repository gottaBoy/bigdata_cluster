## Java
### 安装包下载
https://openjdk.org/projects/jdk8u/
https://www.oracle.com/java/technologies/downloads/#java11-windows

### 环境配置
JAVA8_HOME=D:\minyi\software\java\jdk1.8.0_351
JAVA11_HOME=D:\minyi\software\java\jdk-11.0.17
JAVA_HOME = %JAVA8_HOME%

### CLASSPATH

.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar
### path
%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin

## maven
https://archive.apache.org/dist/maven/maven-3/
MAVEN_HOME=D:\minyi\software\maven\apache-maven-3.6.3
%MAVEN_HOME%\bin

### python
https://www.python.org/downloads/
PYTHON311_HOME=D:\minyi\software\python\Python311
PYTHON_HOME=%PYTHON311_HOME%
%PYTHON_HOME%
%PYTHON_HOME%\Scripts

### virtualbox
https://www.virtualbox.org/wiki/Downloads
http://visualvm.github.io/download.html
Microsoft Visual C++
https://learn.microsoft.com/zh-cn/cpp/windows/latest-supported-vc-redist?vie+vc-170

### vagrant 
https://developer.hashicorp.com/vagrant/downloads
D:\minyi\software\Vagrant\bin

### git
https://git-scm.com/downloads/
D:\minyi\software\git\cmd

### cmder
https://cmder.app/ 
CMDER_HOME=D:\minyi\software\cmder_mini

### tabby
https://tabby.sh/

### prettyzoo
https://github.com/vran-dev/PrettyZoo/releases

### switchhost
https://swh.app/
https://github.com/oldj/SwitchHosts/releases


### Windows安装mysql
https://dev.mysql.com/downloads/mysql/

#### my.ini
```
[mysqld]
# 设置3306端口
port=3306
# 设置mysql的安装目录 ---这里输入你安装的文件路径----
basedir=D:\minyi\software\mysql\mysql-8.0.28-winx64
# 设置mysql数据库的数据的存放目录
datadir=D:\minyi\software\mysql\data
# 允许最大连接数
max_connections=200
# 允许连接失败的次数。
max_connect_errors=10
# 服务端使用的字符集默认为utf8
character-set-server=utf8
# 创建新表时将使用的默认存储引擎
default-storage-engine=INNODB
# 默认使用“mysql_native_password”插件认证
#mysql_native_password
default_authentication_plugin=mysql_native_password
[mysql]
# 设置mysql客户端默认字符集
default-character-set=utf8
[client]
# 设置mysql客户端连接服务端时默认使用的端口
port=3306
default-character-set=utf8
```

#### 安装
//安装mysql  安装完成后Mysql会有一个随机密码
mysqld --initialize --console

//安装mysql服务并启动   
mysqld --install mysql

在本机启动mysql服务
comander + R
services.msc

#### 修改密码
mysql -uroot -p

//修改密码为My@123456
ALTER USER 'root'@'localhost' IDENTIFIED BY 'My@123456';

#### 添加环境变量
MYSQL_HOME=D:\minyi\software\mysql\mysql-8.0.28-winx64
%MYSQL_HOME%\bin


### SQLyog dbeaver.io
https://dbeaver.io/download/
https://cloudbeaver.io/
https://webyog.com/product/sqlyog/
添加用户并授权
create user 'dlink'@'%' identified by 'dlink';
grant select, insert, update, delete, create, drop on dlink.* to 'dlink'@'%' with grant option;

### 激活idea
- [激活idea](https://tobebetterjavaer.com/nice-article/itmind/ideapxideajhideayjjhmideazxjhzcmpjjcyjjhqcyx.html)
- [激活链接2](https://segmentfault.com/a/1190000041984899)
- [激活工具](https://www.lanzoul.com/ikV6Szw3mre)
- [idea](http://idea.955code.com/)
> -javaagent:D:\minyi\software\JetBrains\ja-netfilter-all\ja-netfilter.jar=jetbrains

### winzip
https://www.winrar.com.cn/index.htm

### xmind
https://xmind.cn/
https://www.edrawsoft.cn/mindmaster/

### bigdata
https://www.shouxicto.com/BigData/


### window winutils
https://github.com/steveloughran/winutils
HADOOP_HOME=D:\minyi\bigdata\hadoop-3.1.0
%HADOOP_HOME%\bin
%HADOOP_HOME%\lib
VM options，加上-DHADOOP_USER_NAME=hadoop
C:\Windows\System32\hadoop.ddl

### 技术文档
https://blog.csdn.net/yangbindxj/category_8631133.html


### spark

### scala
https://www.scala-lang.org/
SCALA_HOME=D:\minyi\software\scala

Path 
%SCALA_HOME%\bin
%SCALA_HOME%\jre\bin

ClassPath
.;%SCALA_HOME%\bin;%SCALA_HOME%\lib\dt.jar;%SCALA_HOME%\lib\tools.jar.;

### flink注册
,第一种方式:
-- Flink 连接配置: (可以放入公共参数,及其敏感信息参数)
'hostname' = 'localhost'
,'port' = '3306'
,'username' = 'dlink'
,'password' = 'dlink'
,'server-time-zone' = 'UTC'

-- Flink 连接模板: 
'connector' = 'mysql-cdc'
,'hostname' = 'localhost'
,'port' = '3306'
,'username' = 'dlink'
,'password' = 'dlink'
,'server-time-zone' = 'UTC'
,'scan.incremental.snapshot.enabled' = 'true'
,'debezium.snapshot.mode'='latest-offset'  
,'database-name' = '${schemaName}'
,'table-name' = '${tableName}'

第二种方式:
-- Flink 连接配置: 同第一种方式的连接配置

-- Flink 连接模板: 注意引用变量的前后逗号,使用此方式作业右侧必须开启全局变量
'connector' = 'mysql-cdc'
,${本地}
,'scan.incremental.snapshot.enabled' = 'true'
,'debezium.snapshot.mode'='latest-offset'
,'database-name' = '${schemaName}'
,'table-name' = '${tableName}'

以上配置完成后可在 数据开发->左侧点击 元数据->选中当前创建的数据源 -> 展开库 -> 右键单击 表名 -> 点击 SQL生成 -> 查看FlinkDDL 即可看到成果

### bash
```
$0、$1、$2、$#、$@、$*、$? 

$#：传入脚本的参数个数；
$0:  脚本自身的名称；　　
$1:  传入脚本的第一个参数；
$2:  传入脚本的第二个参数；
$@: 传入脚本的所有参数；
$*：传入脚本的所有参数；
$$:  脚本执行的进程id；
$?:  上一条命令执行后的状态，结果为0表示执行正常，结果为1表示执行异常；
```

### vpn
https://thick.weianbeina.com/
https://www.jianguoyun.com/

### mongodb 27028 
https://www.mongodb.org.cn
https://www.mongodb.com/

### redis
https://github.com/tporadowski/redis/releases


### Netcat使用与分析
https://www.cnblogs.com/-meditation-/articles/15745223.html

- [FAQ-Insufficient number of network buffers](http://study.sf.163.com/documents/read/service_support/dsc-p-b-0011)
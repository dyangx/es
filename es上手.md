# ES 上手 #

### 一、es 基本 ###

1.  es的文件目录结构

   | 目录    | 配置文件          | 描述                                               |
   | ------- | ----------------- | -------------------------------------------------- |
   | bin     |                   | 脚本文件，包括启动的es，安装的插件，运行统计数据等 |
   | config  | elasticsearch.yml | 集群配置文件，user，role absed 相关配置            |
   | JDK     |                   | java运行环境                                       |
   | data    | path.data         | 数据文件                                           |
   | lib     |                   | java类库                                           |
   | logs    | path.log          | 日志文件                                           |
   | modules |                   | 包含所有的es模块                                   |
   | plugins |                   | 包含所有已经安装的文件                             |

2. JVM配置
 ` -config/jvm.options` 

 默认是1GB

3. es 运行多个节点

4. es 查看节点数

` http://localhost:9200/_cat/nodes`






​    
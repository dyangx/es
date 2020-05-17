# ElasticSeach入门
<br/>

## 一、es 基本 ##

1. es的文件目录结构

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

## 二.使用Analyzer进行分词
> es 默认使用Stand Analyzer 作为分词器
### 1.分词器是专门处理分词的组件，Analyzer 由三部分组成：
- Charactter Filters : 针对原始文本处理，例如去除html
- Tokenizer : 按照挥着切分为单词
- Token Filter ： 姜切分的单词进行加工，小写，删除stopwords,增加同义词
### 2.常用的中文分词器
- IK ： 支持自定义词库，支持热更新分词字典
- THULAC ： THU Lexucal Analyzer for Chinese,清华大学自然语言处理和社会人文计算实验室的一套中文分词器

## 三、Search API 概览 ##

1. 指定查询的索引

   | 语法                    | 范围              |
   | ----------------------- | ----------------- |
   | /_search                | 集群上的所有索引  |
   | /index1_search          | index1            |
   | /index1,index-2/_search | index1 和index2   |
   | /index*/_serach         | 以index开头的索引 |
   
2.  URI 查询

   - 使用 ”q“ ，指定查询字符串
   - “query string syntax”,KV 键值对
3. Request Body

![./img/Snipaste_2020-05-17_10-44-51.png](F:\project\ess\es\img\Snipaste_2020-05-17_10-44-51.png)

4. 搜索Response
 ![](F:\project\ess\es\img\Snipaste_2020-05-17_10-45-12.png)



## 四、URI search

1. uri query 实现搜索

   ` GET /movice/_search?q=2012&df=title&sort=year.desc&from=Osize=1O&timeout=is{"Profile ":true}` 

   - q  指定查询语句，使用Query String Syntax

   - df  默认字段，不指定时，会对所有的字段进行查询

   - sort 排序 、from和size用于分页

   - Profile 可以查询查询是符合被执行的

     
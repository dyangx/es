# ElasticSeach入门
<br/>
## 一.使用Analyzer进行分词
> es 默认使用Stand Analyzer 作为分词器
### 1.分词器是专门处理分词的组件，Analyzer 由三部分组成：
- Charactter Filters : 针对原始文本处理，例如去除html
- Tokenizer : 按照挥着切分为单词
- Token Filter ： 姜切分的单词进行加工，小写，删除stopwords,增加同义词
### 2.常用的中文分词器
- IK ： 支持自定义词库，支持热更新分词字典
- THULAC ： THU Lexucal Analyzer for Chinese,清华大学自然语言处理和社会人文计算实验室的一套中文分词器


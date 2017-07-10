# 核心
1. 如何索引？

 对field的考虑？是否需要索引，可能初选在查询条件里面？是否需要analyze(分词，同义等)？

2. 怎么查询？

# 索引(index)

# 类型(type)

# 字段(field)

# 数据类型(filed type)
 1. String
 2. Numeric
 3. Date
 4. Boolean

# 映射(mapping)

# 单词(term)
跟string相关，会对其进行分词等操作(analyze);索引时可指定analyzed (the default),
not_analyzed, or no

# 存储选项
文档本质上就是 term(with filed),倒排后，value为文档id,key为term;而如果找到value和key有如下选项

* value
  1. _source（全量）
  2. store(单独)

* key
  1. _all（ignore field,相当于全文索引）
  如果搜索总是指定field,可以设置为false
  2. term

# 核心
1. 如何索引？

 对field的考虑？是否需要索引，可能出现在查询条件里面？怎么索引，是否需要analyze(分词，同义等)？

2. 怎么查询？

# 基本概念(concept)

1. 文档(document)

2. 索引(index)

3. 类型(type)

4. 字段(field)

5. 数据类型(filed type)
 * String
 * Numeric
 * Date
 * Boolean

6. 映射(mapping)

7. 单词(term)  
跟string相关，会对其进行分词等操作(analyze);索引时可指定analyzed (the default),
not_analyzed, or no

# 存储选项
文档本质上就是 term(with filed),倒排后，value为文档id,key为term;而如何找到value和key有如下选项

* value  
  解决如何找到document field的问题，是从整个文档(_source)里面查出来还是直接得到  
  1. _source（全量）  
  2. store(单独存储，从而直接得到)  
  这个一般用默认即可，即_source

* key
  解决查询匹配空间的问题
  1. _all（ignore field搜索时能搜到,相当于全文索引）
  如果搜索总是指定field,可以设置为false  
  2. term
  是否需要analyze成多个term来进行索引，搜索时也有这个选项:即是否

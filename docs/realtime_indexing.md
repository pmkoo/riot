## 动态修改索引表

悟空引擎支持搜索的同时添加索引（engine.IndexDocument函数），但由于添加索引时会对索引表进行写锁定，因此在添加索引的同时搜索性能会有所下降。请控制添加操作的频率，或者将大量添加操作转移到引擎比较空闲时进行。删除一条文档（engine.RemoveDocument函数）也有同样的问题。

悟空引擎支持缓存插入和删除索引操作，实现批量插入和删除文档，以提高性能。同时删除操作支持从排序器中删除该文档的自定义评分字段。
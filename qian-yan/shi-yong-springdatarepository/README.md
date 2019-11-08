# 4.使用Spring Data Repository

对Spring Data Repository进行抽象的目的就是为了显著减少数据访问层对各种持久化数据而写的模板代码的数量。

> Spring Data Repository文档和您的模块
>
> 这个章节解释Spring Data repository的核心概念和接口。本单内容来自于Spring Data Common模块。针对Java Persistence API\(JPA\)使用配置和代码示例。你应该调整XML命名空间声明和扩展的类型以适应所使用的特定模块。 所有支持repository api的Spring Data 模块都支持包括XML配置在内的 [命名空间引用](https://docs.spring.io/spring-data/jpa/docs/2.2.1.RELEASE/reference/html/#repositories.namespace-reference) 。 [Repository 查询关键字](https://docs.spring.io/spring-data/jpa/docs/2.2.1.RELEASE/reference/html/#repository-query-keywords) 介绍了repository抽象中支持的查询方法关键字。有关模块指定功能的详细信息，请参考指定模块的章节。


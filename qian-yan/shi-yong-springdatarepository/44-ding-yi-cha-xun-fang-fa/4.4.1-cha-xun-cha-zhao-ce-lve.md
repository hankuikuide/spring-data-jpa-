# 4.4.1 查询查找策略

下面的策略可用于repository基础结构来解决查询。使用xml配置，你可以通过query-lookup-strategy属性在命名空间上配置策略。对于java配置，可以使用@Enable${store}$Repository注解r querylookupStrategy属性。 一些策略可以在特定的数据存储中是不支持的。

CREATE 尝试从查询方法名称上构造指定存储的查询。通常的方法是从方法名称中去除一组众所周条的前缀，再解析方法的剩下的部分。关于查询创建可以 “[查询创建](https://docs.spring.io/spring-data/jpa/docs/2.2.1.RELEASE/reference/html/#repositories.query-methods.query-creation)”中了解更多。

USE\_DECLARED\_QUERY 尝试查询到已声明的查询，如果找不到则抛出异常。这个查询可以通过注解来定义或者其他方式。通常查看指定存储的文档，查询存储可用的选项。如果在bootstrap 时repository基础结构中没有找到这个方法已声明的查询，则失败。

CREATE\_IF\_NOT\_FOUND\(默认\)结合了CREATE和USE\_DECLARED\_QUERY，它首先查一下已声明的查询，而后如果没有找到，它会创建一个自定义的以这个名称为命名的查询方法。如果没有你显示的配置的话，这是一个默认的查找策略。它允许按方法名称进行快速的查询定义，也可以根据需要引入已声明的查询来自定义调整这些查询。


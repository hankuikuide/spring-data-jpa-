# Summary

* [Spring Data JPA 参考文档中文版](README.md)
* [前言](前言.md)
    * [1.项目元数据](项目元数据.md)
    * [2.新版特性](新版特性.md)
        * [2.1 Spring Data JPA 1.11的新增功能](21-spring-data-jpa-111的新增功能.md)
        * [2.1 Spring Data JPA 1.10的新增功能](21-spring-data-jpa-110的新增功能.md)
    * [3.依赖](3依赖.md)
        * [3.1 使用Spring Boot进行依赖管理](使用spring-boot进行依赖管理.md)
        * [3.2 Spring 框架](32-spring-框架.md)
    * [4.使用Spring Data Repository](使用spring-data-repository.md)
        * [4.1 核心概念](41-核心概念.md)
        * [4.2 查询方法](42-查询方法.md)
        * 4.3 定义Repository接口
        * [4.4 定义查询方法](44-定义查询方法.md)
        * 4.5 创建Repository实例
        * 4.6 自定义Spring Data Repository实现
        * 4.7 发布聚合根事件
        * [4.8 Spring Data 扩展](spring-data-扩展.md)
* [参考文档](chapter1.md)
    * [5.JPA Repository](jpa-repository.md)
        * [5.1 介绍](51-介绍.md)
            * [5.1.1 Spring 命名空间](511-spring-命名空间.md)
                * 自定义命名空间属性
            * 5.1.2 基于注解的配置
            * [5.1.3 启动模式](513-启动模式.md)
                * 推荐
        * [5.2 持久化实体](52-持久化实体.md)
            * 5.2.1 保存实体
                * 实体状态检测策略
        * [5.3 查询方法](53-查询方法.md)
            * [5.3.1 查询查找策略](531-查询查找策略.md)
                * 声明查询
            * 5.3.2 创建查询
            * [5.3.3 使用JPA命名查询](533-使用jpa命名查询.md)
                * 基于xml的命名查询
                * 基于注解的配置
                * 声明接口
            * [5.3.4 使用@Query](534-使用query.md)
                * 使用高级LIKE表达式
                * 原生查询
            * [5.3.5 使用排序Sort](使用排序sort.md)
            * 5.3.6 使用命名参数
            * 5.3.7 使用SpEL 表达式
            * [5.3.8 修改](538-修改查询.md)
                * 删除
            * 5.3.9 使用查询Hints
            * 5.3.10 配置Fetch和LoadGraphs
            * [5.3.11 映射](5311-映射.md)
                * 基于接口的映射
                * [基于类DTO的映射](基于.md)
                * 动态映射
        * 5.4 存储过程
        * 5.5 Specifications
        * 5.6 Example查询
            * 5.6.1 介绍
            * 5.6.2 Example Matches
            * 5.6.3 执行一个例子
        * [5.7 事务](57-事务.md)
            * 5.7.1 带事务的查询方法
        * 5.8 锁
        * 5.9 审计
            * 5.9.1基础
                * 基于注解的审计元数据
                * 基于接口的审计元数据
                * 审核人员
            * [5.9.2 JPA审计](592-jpa审计.md)
                * 通用审核配置
        * 5.10  其他
            * 5.10.1 在自定义实现中使用JpaContext
            * 5.10.2 合并持久化单元
            * [5.10.3 CDI集成](5103.md)
* 附录


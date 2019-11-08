# 4.2 查询方法

标准的CRUD Reposiotry通常在底层数据存储中进行查询，使用Spring Data 声明这些方法有以下四个步骤：

1.声明一个继承自Repository或它的子类的接口。输入它所查询的domain类和主键ID类型，如下：

```text
interface PersonRepository extends Repository<Person, Long> { … }
```

2. 在接口在声明查询方法

```text
interface PersonRepository extends Repository<Person, Long> {
  List<Person> findByLastname(String lastname);
}
```

3. 设置spring，创建接口的代理实例，可以使用[JavaConfig](https://docs.spring.io/spring-data/jpa/docs/2.2.1.RELEASE/reference/html/#repositories.create-instances.java-config)或[xml configuration](https://docs.spring.io/spring-data/jpa/docs/2.2.1.RELEASE/reference/html/#repositories.create-instances)

a. 要使用java配置，可以创建一个类，如下：

```text
import org.springframework.data.jpa.repository.config.EnableJpaRepositories;

@EnableJpaRepositories
class Config { … }
```

b.要使用xml配置，定义一个bean:   

```text
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
   xmlns:jpa="http://www.springframework.org/schema/data/jpa"
   xsi:schemaLocation="http://www.springframework.org/schema/beans
     https://www.springframework.org/schema/beans/spring-beans.xsd
     http://www.springframework.org/schema/data/jpa
     https://www.springframework.org/schema/data/jpa/spring-jpa.xsd">

   <jpa:repositories base-package="com.acme.repositories"/>

</beans>
```

在这个例子中，使用了JPA命名空间。如果你使用了其他存储的repository抽象，你需要将这个命名空间修改为你的存储模块的适当的命名空间。此外，你应该将替换jpa，如使用mongo.

另外，注意javaconfig注解不会显式的配置package, 因为注解类所在的包是默认配置的，，如果要扫描一个自定义的一个package,可以使用basePackage..属性，basePackage是指定数据存储reposiotry的@Enable${Store}Repository注解的一个属性。

```text
@EnableJpaRepositories(basePackages = "com.mr.upgrade.module.repository")
```

4。 注入repository实例，并使用它，如下：

```text
class SomeClient {

  private final PersonRepository repository;

  SomeClient(PersonRepository repository) {
    this.repository = repository;
  }

  void doSomething() {
    List<Person> persons = repository.findByLastname("Matthews");
  }
}
```

接下来的章节将具体解释每一个步骤：

* 定义Repository接口
* 定义查询方法
* 创建Repository实例
* 自定义Spring Data Repository的实现。






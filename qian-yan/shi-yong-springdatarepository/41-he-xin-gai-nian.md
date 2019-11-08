# 4.1 核心概念

Spring Data repository抽象的主要接口是 Repository. 定义一个Reposiotry需要领域类Domain Class和领域类的ID类型做泛型参数。这个接口主要用做标记接口，用于捕获使用的类型和帮你发现扩展的接口。CrudRepository提供了复杂的针对实体类的CRUD功能。

例3. CrudRepository接口

```text
public interface CrudRepository<T, ID> extends Repository<T, ID> {

  <S extends T> S save(S entity);    

  Optional<T> findById(ID primaryKey); 

  Iterable<T> findAll();               

  long count();                        

  void delete(T entity);               

  boolean existsById(ID primaryKey);   

  // … more functionality omitted.
}
```

保存给定实体

根据id标识返回指定实体

返回所有实体

返回实体的数量

删除给定实体

标识给定的id的实体是否存在。

{% hint style="info" %}
我们也提供 特定技术 的持久化抽象，如JpaRepository或MongoRepository。这些接口继承自Crudepository, 并公开了一些底层的持久 化技术的功能，此外还有与持久化技术无关的功能 如CrudRepository.
{% endhint %}

基于CrudRepository，还有一个PagingAndSortingRepository抽象，它添加了一些简化分页查询实体的方法。

例4. PagingAndSortingRepository 接口

```text
public interface PagingAndSortingRepository<T, ID> extends CrudRepository<T, ID> {

  Iterable<T> findAll(Sort sort);

  Page<T> findAll(Pageable pageable);
}
```

访问User的第2页，页大小为20，你可以这样做：

```text
PagingAndSortingRepository<User, Long> repository = // … get access to a bean
Page<User> users = repository.findAll(PageRequest.of(1, 20));
```

除了查询的方法，count和delete的方法也是可用的，下列代码，显示了定义了一个count查询的接口：

```text
interface UserRepository extends CrudRepository<User, Long> {

  long countByLastname(String lastname);
}
```

下列代码，显示了定义了一个delete方法的接口。

```text
interface UserRepository extends CrudRepository<User, Long> {

  long deleteByLastname(String lastname);

  List<User> removeByLastname(String lastname);
}
```


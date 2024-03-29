# 3.依赖

每个Spring data 模块起始日期不同，它们有不同的主版本号和次版本号， 所以查询兼容版本最简单的方法是使用我们已定义好的兼容版本Spring Data Release Train BOM,在Maven项目中，你可以在POM的&lt;DependencyManagement \/&gt;中声明，如下：

例1，使用Spring Data release train BOM

&lt;dependencyManagement&gt; &lt;dependencies&gt; &lt;dependency&gt; &lt;groupId&gt;org.springframework.data&lt;\/groupId&gt; &lt;artifactId&gt;spring-data-releasetrain&lt;\/artifactId&gt; &lt;version&gt;Moore-SR1&lt;\/version&gt; &lt;scope&gt;import&lt;\/scope&gt; &lt;type&gt;pom&lt;\/type&gt; &lt;\/dependency&gt; &lt;\/dependencies&gt; &lt;\/dependencyManagement&gt;

当前发布的train version是 Moore-SR1, train的名字按字母升序排列，当前可用的train在[here. ](https://github.com/spring-projects/spring-data-commons/wiki/Release-planning)版本名称遵循以下格式：${name}-${release}, 其中release可以是下列中的一个：

* BUILD-SNAPSHOT: 构建快照
* M1,M2等：里程碑
* RC1，RC2等：发布候选版
* RELEASE:GA发布版
* SR1，SR2等：服务发布版

在我们的[Spring Data example repository](https://github.com/spring-projects/spring-data-examples/tree/master/bom)中可以找到使用BOMs的工作示例，在示例中，你可以在&lt;dependencies&gt;中不指定版本的情况使用spring data模块，如下： 例2：声明一个Spring Data模块的依赖：

`<dependencies> <dependency> <groupId>org.springframework.data</groupId> <artifactId>spring-data-jpa</artifactId> </dependency> <dependencies>`


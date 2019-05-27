将从class path中读取all.sql文件
可以将 sql 文件放在maven项目下的resources 之下，编译器会自动将其编译至 class path 之下，进而可以被读取到

```xml
<dependency>
	<groupId>com.gitee.ruanzy</groupId>
	<artifactId>sqlTemplate-spring-boot-starter</artifactId>
	<version>1.0.0</version>
</dependency>
```

*指令*
#sql 指令
#sql 指令用于定义 sql 模板，如下是代码示例：
```sql
#sql("findGirl")
  select * from girl where age > ? and age < ? and weight < 50
#end
```

#para 指令(简写#p)
#para 指令用于生成 sql 模板中的问号占位符以及问号占位符所对应的参数值，如下是代码示例：
```sql
#sql("findGirl")
  select * from girl where age > #para(age) and weight < #para(weight)
#end
```
#### 引入sqlTemplate
```xml
<dependency>
	<groupId>com.gitee.ruanzy</groupId>
	<artifactId>sqlTemplate-spring-boot-starter</artifactId>
	<version>1.0.0</version>
</dependency>
```
application.properties配置

sqlTemplate.path = sql 默认sql

该目录下新建一个名为all_sql.sql， 其中包含所有的sql引用

```json
#namespace("user")
  #include("user.sql")
#end
#namespace("role")
  #include("role.sql")
#end
#namespace("resources")
  #include("resources.sql")
#end
#namespace("log")
  #include("log.sql")
#end
```
项目启动时将加载classpath下sql目录里的all_sql.sql，从而加载所有sql文件


#### 动态sql相关指令
##### #sql 指令
#sql 指令用于定义 sql 模板，如下是代码示例：
```sql
#sql('info')
	select * from users where users.username=#p(username)
#end
```

##### #para 指令(简写#p)
#para 指令用于生成 sql 模板中的问号占位符以及问号占位符所对应的参数值，如下是代码示例：
```sql
#sql("findGirl")
  select * from girl where age > #para(age) and weight < #para(weight)
#end
```

##### #if 指令
```sql
#sql('list')
	select * from users where 1=1
	#if(username)
	and username like #paraLike(username)
	#end
	order by id DESC
	limit #p(offset),#p(pagesize)
#end
```

#### Java使用sqlTemplate
```java
Map<String, Object> p = new HashMap<String, Object>();
p.put("username", "haha");
BoundSql boundSql = sqlTemplate.getBoundSql("user.info", p);
String sql = boundSql.getSql();
Object[] args = boundSql.getParameters();
Map<String, Object> map = jdbcTemplate.queryForMap(sql, args);
```
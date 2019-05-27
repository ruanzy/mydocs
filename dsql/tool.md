**简要描述：** 

- 用户删除接口

**请求URL：** 
- ` http://xx.com/api/user/del `
  
**请求方式：**
- POST 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|username |是  |string |用户名   |
|password |是  |string | 密码    |
|name     |否  |string | 昵称    |

 **返回示例**

```java
Map<String, Object> p = new HashMap<String, Object>();
String u = WebContext.getUsername();
p.put("username", u);
SqlPara sqlPara = SqlUtil.getSqlPara("user.info", p);
String sql = sqlPara.getSql();
Object[] args = sqlPara.getPara();
Map<String, Object> map = jdbcTemplate.queryForMap(sql, args);
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|groupid |int   |用户组id，1：超级管理员；2：普通用户  |

 **备注** 

- 更多返回错误代码请看首页的错误代码描述
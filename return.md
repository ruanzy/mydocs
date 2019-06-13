##### 退库列表查询

**请求URL：** ` material/return/list/{projectId} `
  
**请求方式：** GET 

**CONTENT-TYPE：** `application/x-www-form-urlencoded`

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|username |是  |string |用户名   |
|password |是  |string | 密码    |
|captcha |是  |string | 验证码    |

 **返回示例**

```json
  {
    "rows": [...];
    "total": 100,
    "totalPages": 3,
    "size": 10,
    "page": 1,
  }
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|rows |Array   |当前页数据 |
|total |Integer   |总记录数  |
|totalPages |Integer   |总页数  |
|size |Integer   |每页记录数  |
|page |Integer   |当前页  |


**rows参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----|
|ID |String   |唯一标识 |
|PROJECT_ID |String   |项目ID |
|RETURNS_CODE |String   |退库编码 |
|PO_CODE |String   |合同编码 |
|PO_DESC |String   |合同名称  |
|WAREHOUSE_DESC |String   |仓库名称  |
|SUPPLIER_DESC |String   |供应商名称  |
|MTO_AREA_DESC |String   |使用区域  |

##### 退库列表查询

**请求URL：** ` material/return/list/{projectId} `
  
**请求方式：** GET 

**CONTENT-TYPE：** `application/x-www-form-urlencoded`

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|PROJECT_ID |是  |string |项目ID   |
|RETURNS_CODE |否  |string |退库号   |
|WAREHOUSE_CODE |否  |string | 仓库ID    |
|USED_TO |否  |string | 使用区域ID    |
|PO_CODE |否  |string | 合同编码    |
|SUPPLIER |否  |string | 供应商ID    |
|RECEIVED_BY |否  |string | 接收人ID    |
|RETURNED_BY_NAME |否  |string | 退库人ID    |
|RETURNS_STATUS |否  |string | 退库状态    |
|RETURN_DATE_BEGIN |否  |Date | 退库开始日期    |
|RETURN_DATE_END |否  |Date | 退库结束日期    |

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
|WAREHOUSE_CODE |String   |仓库编号 |
|WAREHOUSE_DESC |String   |仓库名称  |
|SUPPLIER_DESC |String   |供应商名称  |
|USED_TO |String   |使用区域ID  |
|MTO_AREA_DESC |String   |使用区域  |
|RETURNS_STATUS |String   |退库状态  |
|RECEIVED_BY |String   |接收人ID  |
|RETURN_DATE |Date   |退库日期  |
|RETURN_REASON |String   |退库原因  |
|INSPECTOR |String   |校验人  |
|SUPPLIER |String   |供应商ID  |
|RETURNED_BY_NAME |String   |退库人  |
|RETURN_NOTES |String   |退库说明  |
|INSERT_USER |String   |创建人  |
|INSERT_DATE |Date   |创建时间  |
|MODIFY_USER |String   |修改人  |
|MODIFY_DATE |Date   |修改时间  |

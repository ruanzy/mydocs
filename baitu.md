##### 设计评审列表查询

**请求URL：** ` /design/review/list `
  
**请求方式：** GET 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|poId |否  |string |设计合同ID   |
|batch |否  |string |批次号或批次名称   |
|status |否  |string |状态   |

 **返回示例**

```json
{
    "rows": [...],
    "total": 100,
    "totalPages": 3,
    "size": 10,
    "page": 1,
}
```

**rows明细** 
```json
{
    "id": 1
    "batchNo": 1
    "batchName": "第一批"
    "drawingsNumber": 5
    "applyTime": 1564462242000
    "approvalTime": 1564462242000
    "status": '1'
    "designPoId": "02"
    "insertUser": "admin"
    "insertDate": 1564462242000
    "modifyUser": "admin"
    "modifyDate": 1564462242000
}
```

 **返回说明** 
 
|参数名|类型|说明|
|:-----  |:-----|-----                           |
|rows |array   |当前页数据|
|total |int   |总记录数 |
|totalPages |int   |总页数  |
|size	 |int   |每页记录数  |
|page |int   |当前页 |
 
 **rows说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|id |int   |唯一标识 ID|
|batchNo |int   |批次号  |
|batchName |string   |批次名称  |
|drawingsNumber |int   |图纸数量  |
|applyTime |string   |申请时间  |
|approvalTime |string   |审批时间  |
|status |string   |状态  |
|designPoId |string   |设计合同  |
|insertUser |string   |新增用户  |
|insertDate |string   |新增时间  |
|modifyUser |string   |修改用户  |
|modifyDate |string   |修改时间  |



##### 设计评审新增

**请求URL：** ` /design/review `
  
**请求方式：** POST 

**CONTENT-TYPE：** `application/json`

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|batchNo |是 |int   |批次号  |
|batchName |是 |string   |批次名称  |
|drawingsNumber |是 |int   |图纸数量  |
|applyTime |是 |string   |申请时间  |
|designPoId |是 | string   |设计合同  |

 **返回示例**

```json
"id": 1
"batchNo": 1
"batchName": "第一批"
"drawingsNumber": 5
"applyTime": 1564462242000
"approvalTime": 
"status": '1'
"designPoId": "02"
"insertUser": "admin"
"insertDate": 1564462242000
"modifyUser": "admin"
"modifyDate": 1564462242000
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|id |int   |唯一标识 ID|
|batchNo |int   |批次号  |
|batchName |string   |批次名称  |
|drawingsNumber |int   |图纸数量  |
|applyTime |string   |申请时间  |
|approvalTime |string   |审批时间  |
|status |string   |状态  |
|designPoId |string   |设计合同  |
|insertUser |string   |新增用户  |
|insertDate |string   |新增时间  |
|modifyUser |string   |修改用户  |
|modifyDate |string   |修改时间  |


##### 设计评审新增成果

**请求URL：** ` /design/review/addResult `
  
**请求方式：** POST 

**CONTENT-TYPE：** `application/json`

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|reviewId |是  |string |评审ID, 唯一标识ID   |
|resultVersionIds |是  |array |设计成果版本ID(多个)   |


##### 设计评审删除(同时删除成果)

**请求URL：** ` /design/review/{id} `
  
**请求方式：** DELETE 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|id |是  |string |唯一标识ID   |

 **返回示例**

```json
  "code": 10000
  "message": ""
```


##### 设计评审修改

**请求URL：** ` /design/review/ `
  
**请求方式：** PATCH

**CONTENT-TYPE：** `application/json`

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|id |是 |int   |唯一标识 |
|batchNo |是 |int   |批次号  |
|batchName |是 |string   |批次名称  |
|drawingsNumber |是 |int   |图纸数量  |
|applyTime |是 |string   |申请时间  |
|designPoId |是 | string   |设计合同  |

 **返回示例**

```json
"id": 1
"batchNo": 1
"batchName": "第一批"
"drawingsNumber": 5
"applyTime": 1564462242000
"approvalTime": 
"status": '1'
"designPoId": "02"
"insertUser": "admin"
"insertDate": 1564462242000
"modifyUser": "admin"
"modifyDate": 1564462242000
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|id |int   |唯一标识 ID|
|batchNo |int   |批次号  |
|batchName |string   |批次名称  |
|drawingsNumber |int   |图纸数量  |
|applyTime |string   |申请时间  |
|approvalTime |string   |审批时间  |
|status |string   |状态  |
|designPoId |string   |设计合同  |
|insertUser |string   |新增用户  |
|insertDate |string   |新增时间  |
|modifyUser |string   |修改用户  |
|modifyDate |string   |修改时间  |

##### 设计评审查询

**请求URL：** ` /design/review/{id} `
  
**请求方式：** GET

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|id |是 |int   |唯一标识 |

 **返回示例**

```json
"id": 1
"batchNo": 1
"batchName": "第一批"
"drawingsNumber": 5
"applyTime": 1564462242000
"approvalTime": 
"status": '1'
"designPoId": "02"
"insertUser": "admin"
"insertDate": 1564462242000
"modifyUser": "admin"
"modifyDate": 1564462242000
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|id |int   |唯一标识 ID|
|batchNo |int   |批次号  |
|batchName |string   |批次名称  |
|drawingsNumber |int   |图纸数量  |
|applyTime |string   |申请时间  |
|approvalTime |string   |审批时间  |
|status |string   |状态  |
|designPoId |string   |设计合同  |
|insertUser |string   |新增用户  |
|insertDate |string   |新增时间  |
|modifyUser |string   |修改用户  |
|modifyDate |string   |修改时间  |


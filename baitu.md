##### 设计评审列表查询

**请求URL：** ` /design/review/list `
  
**请求方式：** GET 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|poId |否  |string |设计合同ID   |
|batch |否  |string |批次号或批次名称   |
|status |否  |string |状态   |
|resultVersion |是 | string   |白图: 1, 蓝图: 2  |

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
    "id": "3334dc36737f441fbe09ad5a0abb6ec1",
    "batchNo": "20190807001",
    "batchName": "第一批",
    "drawingsNumber": 5,
    "applyTime": 1564462242000,
    "approvalTime": 1564462242000,
    "status": '1',
    "designPoId": "8ac4c0ff6c40f347016c41c5fb950000",
    "insertUser": "admin",
    "insertDate": 1564462242000,
    "modifyUser": "admin",
    "modifyDate": 1564462242000,
    "projectId": "8ac4edf56b2c1060016b2c15d0bd0000",
    "releaseUserName": null,
    "resultVersion": "1",
    "hasResult": 1
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
|id |string   |唯一标识 ID|
|batchNo |string   |批次号  |
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
|projectId |string   |项目ID|
|releaseUserName |string   |发布者|
|resultVersion |string   |白图: 1, 蓝图: 2  |
|hasResult |int   |是否有成果|


##### 设计评审批次序列号获取

**请求URL：** ` /design/review/nextBatchNo `
  
**请求方式：** GET 

**参数：** 
eg: ?time=20190805

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|time |是 |string   |当前时间戳  如: 20190805|

 **返回示例**

```json
20190805085
```
>999抛出异常信息


##### 设计评审成果树查询

**请求URL：** ` /design/review/resultTree `
  
**请求方式：** GET 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|poId |是  |string |设计合同ID   |
|reviewId |是  |string |设计成果评审ID   |
|resultVersion |是  |string   |白图: 1, 蓝图: 2  |

 **返回示例**

```json
[{
	"children": [{
		"resultCode": "111#0",
		"files": [],
		"pid": "40287f816c514ae5016c518d06d80000",
		"disabled": 0,
		"id": "f40f847a859e4a0c806cfc4a7014fbde",
		"label": "test 1【1 白图】",
		"type": 2,
		"resultVersionId": "b33f6806ea3b4b2db785a29b1dcb557a"
	}],
	"pid": "0",
	"disabled": null,
	"id": "40287f816c514ae5016c518d06d80000",
	"label": "111",
	"type": 1
}, {
	"children": [{
		"resultCode": "222#3",
		"files": [],
		"pid": "40287f816c514ae5016c518d7bcf0001",
		"disabled": 0,
		"id": "097573e0dc1f4bca9e3318d54c388821",
		"label": "4【1 白图】",
		"type": 2,
		"resultVersionId": "f48a162664464f1cb75f7846dfbfda67"
	}, {
		"resultCode": "222#1",
		"files": [],
		"pid": "40287f816c514ae5016c518d7bcf0001",
		"disabled": 0,
		"id": "2e653e9e940544c6b5f8fdea79507ce8",
		"label": "2【1 白图】",
		"type": 2,
		"resultVersionId": "b11a2500f3724f0c84e197ef9db1ab03"
	}, {
		"resultCode": "222#0",
		"files": [],
		"pid": "40287f816c514ae5016c518d7bcf0001",
		"disabled": 0,
		"id": "b859fb48c285489f8e59fe30f00eaad8",
		"label": "1【1 白图】",
		"type": 2,
		"resultVersionId": "ce17244807a940ce8bd2c44a4a31477e"
	}],
	"pid": "0",
	"disabled": null,
	"id": "40287f816c514ae5016c518d7bcf0001",
	"label": "222",
	"type": 1
}]
```
>999抛出异常信息

##### 设计评审新增

**请求URL：** ` /design/review `
  
**请求方式：** POST 

**Content-Type：** `application/json`

**参数示例**

```json
{
    "id": "1755c501b1cc4e06ac98737edcc5db6b",
    "batchNo": "20190807003",
    "batchName": "第一批",
    "drawingsNumber": 5,
    "applyTime": 1564462242000,
    "designPoId": "8ac4c0ff6c40f347016c41c5fb950000",
    "projectId": "8ac4edf56b2c1060016b2c15d0bd0000",
    "resultVersion": 1,
    "results": [1, 2, ...]
}
```

**参数说明：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|id |是 |string   |唯一标识ID  |
|batchNo |是 |string   |批次号  |
|batchName |是 |string   |批次名称  |
|drawingsNumber |是 |int   |图纸数量  |
|applyTime |是 |string   |申请时间  |
|designPoId |是 | string   |设计合同  |
|projectId |是 | string   |项目ID|
|resultVersion |是 | string   |白图: 1, 蓝图: 2  |
|results |是 |array   |成果版本ID  |


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
|id |string   |唯一标识 ID|
|batchNo |string   |批次号  |
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
|projectId |string   |项目ID|
|releaseUserName |string   |发布者|
|resultVersion |string   |白图: 1, 蓝图: 2  |


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
|results |是 | array   |成果版本ID  |

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
"projectId": "8ac4edf56b2c1060016b2c15d0bd0000",
"releaseUserName": null,
"resultVersion": "1",
"results": [1, 2, ...]
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|id |string   |唯一标识 ID|
|batchNo |string   |批次号  |
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
|projectId |string   |项目ID|
|releaseUserName |string   |发布者|
|resultVersion |string   |白图: 1, 蓝图: 2  |
|results |array   |成果版本ID  |

##### 设计评审查询

**请求URL：** ` /design/review/{id} `
  
**请求方式：** GET

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|id |是 |string   |唯一标识 |

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
"projectId": "8ac4edf56b2c1060016b2c15d0bd0000",
"releaseUserName": null,
"resultVersion": "1",
"results": [1, 2, ...]
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|id |string   |唯一标识 ID|
|batchNo |string   |批次号  |
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
|projectId |string   |项目ID|
|releaseUserName |string   |发布者|
|resultVersion |string   |白图: 1, 蓝图: 2  |
|results |array   |成果版本ID  |


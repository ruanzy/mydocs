##### EWBS列表查询

**请求URL：** ` /design/ewbs/list `
  
**请求方式：** GET 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|poId |是  |string |设计合同ID   |

 **返回示例**

```json
"buildStructure": "05"
"children": […]
"code": "0102"
"pcode": "01"
"complete": 56.87
"designPhase": "02"
"designPoId": "02"
"designSpecial": "03"
"endTime": 1564462242000
"id": 1
"name": "AA"
"pid": 0
"planEndTime": 1564462237000
"planStartTime": 1564462234000
"purchaseTender": "06"
"remark": "KKK"
"resultType": "04"
"startTime": 1564462239000
"weight": 37.86
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|id |int   |唯一标识 ID|
|pcode |string   |上级编码  |
|code |string   |编码  |
|name |string   |名称  |
|pid |string   |上级ID  |
|designPhase |string   |设计阶段  |
|designSpecial |string   |设计专业  |
|resultType |string   |成果类型  |
|buildStructure |string   |建筑结构  |
|purchaseTender |string   |采购标包  |
|planStartTime |string   |计划开始时间  |
|planEndTime |string   |计划结束时间  |
|startTime |string   |实际开始时间 |
|endTime |string   |实际结束时间  |
|remark |string   |备注  |
|weight |string   |计划权重  |
|complete |string   |实际完成比例  |
|designPoId |string   |设计合同  |


##### EWBS新增

**请求URL：** ` /design/ewbs `
  
**请求方式：** POST 

**CONTENT-TYPE：** `application/json`

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|code|是 |string   |编码  |
|name |是 |string   |名称  |
|pcode |是 string   |上级编码  |
|pid |是 |string   |上级ID  |
|designPhase |否 |string   |设计阶段  |
|designSpecial |否 |string   |设计专业  |
|resultType |否 | string   |成果类型  |
|buildStructure |否 |string   |建筑结构  |
|purchaseTender |否 | string   |采购标包  |
|planStartTime |是 | string   |计划开始时间  |
|planEndTime |是 | string   |计划结束时间  |
|startTime |否 | string   |实际开始时间 |
|endTime |否 | string   |实际结束时间  |
|remark |否 | string   |备注  |
|weight |否 | string   |计划权重  |
|complete |否 | string   |实际完成比例  |
|designPoId |是 | string   |设计合同  |

 **返回示例**

```json
"buildStructure": "05"
"code": "0102"
"pcode": "01"
"complete": 56.87
"designPhase": "02"
"designPoId": "02"
"designSpecial": "03"
"endTime": 1564462242000
"id": 1
"name": "AA"
"pid": 0
"planEndTime": 1564462237000
"planStartTime": 1564462234000
"purchaseTender": "06"
"remark": "KKK"
"resultType": "04"
"startTime": 1564462239000
"weight": 37.86
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|id |int   |唯一标识 |
|code |string   |编码  |
|name |string   |名称  |
|pcode |string   |上级编码  |
|pid |string   |上级ID  |
|designPhase |string   |设计阶段  |
|designSpecial |string   |设计专业  |
|resultType |string   |成果类型  |
|buildStructure |string   |建筑结构  |
|purchaseTender |string   |采购标包  |
|planStartTime |string   |计划开始时间  |
|planEndTime |string   |计划结束时间  |
|startTime |string   |实际开始时间 |
|endTime |string   |实际结束时间  |
|remark |string   |备注  |
|weight |string   |计划权重  |
|complete |string   |实际完成比例  |
|designPoId |string   |设计合同  |

##### EWBS删除

**请求URL：** ` /design/ewbs/{id} `
  
**请求方式：** DELETE 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|id |是  |string |唯一标识ID   |

 **返回示例**

```json
{
  "code"：10000
  "message": "当前EWBS项存在下级，不能被删除"
}
```


##### EWBS修改

**请求URL：** ` /design/ewbs/ `
  
**请求方式：** PATCH

**CONTENT-TYPE：** `application/json`

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|id |是 |int   |唯一标识 |
|code|否 |string   |编码  不可修改|
|name |是 |string   |名称  |
|pcode |否 |string   |上级编码  不可修改|
|pid |是 |string   |上级ID  |
|designPhase |否 |string   |设计阶段  |
|designSpecial |否 |string   |设计专业  |
|resultType |否 | string   |成果类型  |
|buildStructure |否 |string   |建筑结构  |
|purchaseTender |否 | string   |采购标包  |
|planStartTime |是 | string   |计划开始时间  |
|planEndTime |是 | string   |计划结束时间  |
|startTime |否 | string   |实际开始时间 |
|endTime |否 | string   |实际结束时间  |
|remark |否 | string   |备注  |
|weight |否 | string   |计划权重  |
|complete |否 | string   |实际完成比例  |
|designPoId |是 | string   |设计合同  |

**注意**
EWBS存在下级，则不能修改EWBS编码和计划开始时间、计划结束时间。
EWBS底层项被设计包关联后，则不能修改EWBS编码和计划开始时间、计划结束时间。

 **返回示例**

```json
"buildStructure": "05"
"code": "0102"
"pcode": "01"
"complete": 56.87
"designPhase": "02"
"designPoId": "02"
"designSpecial": "03"
"endTime": 1564462242000
"id": 1
"name": "AA"
"pid": 0
"planEndTime": 1564462237000
"planStartTime": 1564462234000
"purchaseTender": "06"
"remark": "KKK"
"resultType": "04"
"startTime": 1564462239000
"weight": 37.86
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|id |int   |唯一标识 |
|code |string   |编码  |
|name |string   |名称  |
|pcode |string   |上级编码  |
|pid |string   |上级ID  |
|designPhase |string   |设计阶段  |
|designSpecial |string   |设计专业  |
|resultType |string   |成果类型  |
|buildStructure |string   |建筑结构  |
|purchaseTender |string   |采购标包  |
|planStartTime |string   |计划开始时间  |
|planEndTime |string   |计划结束时间  |
|startTime |string   |实际开始时间 |
|endTime |string   |实际结束时间  |
|remark |string   |备注  |
|weight |string   |计划权重  |
|complete |string   |实际完成比例  |
|designPoId |string   |设计合同  |


##### EWBS查询

**请求URL：** ` /design/ewbs/{id} `
  
**请求方式：** GET

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|id |是 |int   |唯一标识 |

 **返回示例**

```json
"buildStructure": "05"
"code": "0102"
"pcode": "01"
"complete": 56.87
"designPhase": "02"
"designPoId": "02"
"designSpecial": "03"
"endTime": 1564462242000
"id": 1
"name": "AA"
"pid": 0
"planEndTime": 1564462237000
"planStartTime": 1564462234000
"purchaseTender": "06"
"remark": "KKK"
"resultType": "04"
"startTime": 1564462239000
"weight": 37.86
"hasRelation": 0
"hasSub": 0
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|id |int   |唯一标识 |
|code |string   |编码  |
|name |string   |名称  |
|pcode |string   |上级编码  |
|pid |string   |上级ID  |
|designPhase |string   |设计阶段  |
|designSpecial |string   |设计专业  |
|resultType |string   |成果类型  |
|buildStructure |string   |建筑结构  |
|purchaseTender |string   |采购标包  |
|planStartTime |string   |计划开始时间  |
|planEndTime |string   |计划结束时间  |
|startTime |string   |实际开始时间 |
|endTime |string   |实际结束时间  |
|remark |string   |备注  |
|weight |string   |计划权重  |
|complete |string   |实际完成比例  |
|designPoId |string   |设计合同  |
|hasSub |string   |是否有子节点  |
|hasRelation |string   |是否被设计包引用 |

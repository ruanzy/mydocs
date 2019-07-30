##### EWBS列表查询

**请求URL：** ` /design/ewbs/list `
  
**请求方式：** GET 

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|poNo |否  |string |设计合同编号   |

 **返回示例**

```json
"buildStructure": "05"
"children": […]
"code": "01"
"complete": 56.87
"designPhase": "02"
"designPoNo": "02"
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
|pid |string   |上级编码  |
|designPhase |string   |设计阶段  |
|designSpecial |string   |设计专业  |
|resultType |string   |成果类型  |
|buildStructure |string   |建筑结构  |
|buildStructure |string   |建筑结构  |
|purchaseTender |string   |采购标包  |
|planEndTime |string   |计划结束时间  |
|startTime |string   |实际开始时间 |
|endTime |string   |实际结束时间  |
|remark |string   |备注  |
|weight |string   |计划权重  |
|complete |string   |实际完成比例  |
|designPoNo |string   |设计合同  |

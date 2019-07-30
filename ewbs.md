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
|code |int   |错误码，0：OK；非0：异常 |
|data |Object   |返回数据  |

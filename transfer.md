##### 退库列表查询

**请求URL：** ` material/return `
  
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
    "code": 0,
    "data": {
      "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJmcm9tX3V..."
    }
  }
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|code |int   |错误码，0：OK；非0：异常 |
|data |Object   |返回数据  |

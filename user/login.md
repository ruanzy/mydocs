**简要描述：** 

- 用户登录接口

**请求URL：** ` user/login `
  
**请求方式：** POST 

**请求数据类型：** `application/json`

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

 **备注** 

- 更多返回错误代码请看首页的错误代码描述
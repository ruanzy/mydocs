**简要描述：** 

- 用户登录接口

**请求URL：** 
- ` http://xx.com/api/user/login `
  
**请求方式：**
- POST 

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
      "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJmcm9tX3VzZXIiOiJCIiwidGFyZ2V0X3VzZXIiOi.rSWamyAYwuHCo7IFAgd1oRpSP7nzL7BF5t7ItqpKViM"
    }
  }
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|code |int   |请求相应码，0：OK；非0：异常  |
|data |Object   |返回数据  |

 **备注** 

- 更多返回错误代码请看首页的错误代码描述
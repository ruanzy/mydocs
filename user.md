##### 用户登录

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

---

##### 用户信息

**请求URL：** ` /user/info `
  
**请求方式：** GET 

**请求数据类型：** `application/x-www-form-urlencoded`

**参数：** 

|参数名|必选|类型|说明|
|:----    |:---|:----- |-----   |
|username |是  |string |用户名   |

 **返回示例**

```json
  {
    "username": "ruanzy",
    "avatar": "./static/1.png",
    "roles": ["admin", "operator"],
    "menus": [...]
  }
```

 **返回参数说明** 

|参数名|类型|说明|
|:-----  |:-----|-----                           |
|username |String   |用户名  |
|avatar |String   |用户头像  |
|roles |Array   |角色数组  |
|menus |Array   |菜单数组  |

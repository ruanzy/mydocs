**简要描述：** 

- 登录后获得用户信息接口

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

 **备注** 

- 更多返回错误代码请看首页的错误代码描述
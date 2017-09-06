
## 初始获取access_token接口

- 功能描述: 获取`access_token`
- 请求地址: `http://domain/uaa/oauth/token`
- 请求动作: `POST`
- 请求示例: `http://domain/uaa/oauth/token?grant_type=password&username=maj&password=maj`  
      Authorization：  
         - Type:Base Auth  
         - Username:android  
         - Password:android

- 返回示例
```
{
    "access_token": "bdfc82c8-8020-4f50-8c69-125b34594a46",
    "token_type": "bearer",
    "refresh_token": "6fcec503-ead9-414c-87ee-9af13a855e03",
    "expires_in": 36464,
    "scope": "xx"
}
```
## 获取refresh_token接口

- 功能描述: 获取refresh_token
- 请求地址: `http://domain/uaa/oauth/token`
- 请求动作: `POST`
- 请求示例: `http://domain/uaa/oauth/token?grant_type=refresh_token&refresh_token=6fcec503-ead9-414c-87ee-9af13a855e03`  
      Authorization：  
      - Type:Base Auth  
      - Username:android  
      - Password:android

- 返回示例
```
{
    "access_token": "c2b3f96b-a7e7-4c84-9a5a-1041aa890b24",
    "token_type": "bearer",
    "refresh_token": "6fcec503-ead9-414c-87ee-9af13a855e03",
    "expires_in": 43199,
    "scope": "xx"
}
```
## 注销接口

- 功能描述: 注销access_token和refresh_token的授权
- 请求地址: `http://domain/uaa/oauth/token`
- 请求动作: `DELETE`
- 请求示例: `http://domain/uaa/oauth/token?access_token=5c0b6d1c-94e3-4e82-8acb-e4a266e5ddf3` 
    ​          
    Authorization：  
    - Type:Base Auth  
      - Username:android  
      - Password:android

- 成功返回示例
```
{
    "status": "SUCCESS",
    "data": "注销成功"
}
```
- 失败返回示例
```
{
    "status": "FAILURE",
    "data": "注销失败"
}
```

- 请求失败返回示例：  
```
{
  "error": "access_denied",
  "error_description": "不允许访问"
} 
```
# 5.1 UserController测试用例

### 5.1.1 查询单个用户信息

- 功能描述: 根据id查询单个用户信息
- 请求地址: `http://domain/uaa/sysusers/{id}?access_token=ACCESS_TOKEN`
- 请求动作: `GET`
- 请求示例: `http://domain/uaa/sysusers/6?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`  

- 返回示例  
```
{
    "status": "SUCCESS",
    "data": {
        "id": 6,
        "username": "wyf",
        "password": "$2a$10$WjApX3bMw1KfzckGCCOB.eXRNY61ZcwsqpNzc2yiHtjsqnS3LmXAS",
        "employeeId": null,
        "firstName": null,
        "lastName": null,
        "email": null,
        "roles": [
            {
                "id": 4,
                "name": "普通用户",
                "value": "ROLE_USER",
                "authorities": []
            }
        ],
        "authorities": [],
        "enabled": true,
        "credentialsNonExpired": true,
        "accountNonLocked": true,
        "accountNonExpired": true
    }
}
```

### 5.1.2 查询用户列表接口

- 功能描述: 查询用户信息列表
- 请求地址: `http://domain/uaa/sysusers?access_token=ACCESS_TOKEN`
- 请求动作: `GET`
- 请求示例: `http://domain/uaa/sysusers?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`  

- 返回示例
  ```
  {
      "status": "SUCCESS",
      "data": {
          "content": [
              {
                  "id": 26,
                  "username": "lunx",
                  "password": "$2a$10$dZFlEj9zxQX3/2Ju15FUQeJV8wSrAltnqLlTGuQH5or8Jv3vmObQK",
                  "employeeId": 1003,
                  "firstName": null,
                  "lastName": null,
                  "email": null,
                  "roles": [
                      {
                          "id": 5,
                          "name": "收费员",
                          "value": "ROLE_CHARGER",
                          "authorities": [
                              {
                                  "id": 34,
                                  "name": "车辆驶入",
                                  "value": "order-order-driveIn"
                              }
                          ]
                      }
                  ],
                  "authorities": [

                      {
                          "authority": "order-order-driveIn"
                      }
                  ],
                  "enabled": true,
                  "accountNonLocked": true,
                  "credentialsNonExpired": true,
                  "accountNonExpired": true
              }
          ],
          "last": true,
          "totalElements": 4,
          "totalPages": 1,
          "number": 0,
          "size": 20,
          "sort": null,
          "first": true,
          "numberOfElements": 4
      }
  }
  ```

### 5.1.3 添加新用户接口

- 功能描述:  添加新用户
- 请求地址: `http://domain/uaa/sysusers?access_token=ACCESS_TOKEN`
- 请求动作: `POST`
- 请求示例: `http://domain/uaa/sysusers?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`  

- POST数据示例
  ```
  {
  	"username":"zhang",
  	"password":"zzzzzz"
  	"roles":{
  	    "id":1001;
  	}
  }
  ```


### 5.1.4 更新用户信息接口

- 功能描述:  根据id更新用户信息
- 请求地址: `http://domain/uaa/sysusers/{id}?access_token=ACCESS_TOKEN`
- 请求动作: `PUT`
- 请求示例: `http://domain/uaa/sysusers/55?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`  

- PUT数据示例
 ```
 {
       "employeeId": 1022,
         "roles": [
             {
                 "id": 5
             }
         ]
 }
 ```
### 5.1.5 根据用户名查找用户信息接口

- 功能描述:  根据用户名查找用户信息
- 请求地址: `http://domain/uaa/sysusers/query?username=USERNAME&access_token=ACCESS_TOKEN`
- 请求动作: `GET`
- 请求示例: `http://domain/uaa/sysusers/query?username=maj&access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`  

- 返回数据示例
  ```
  {
      "status": "SUCCESS",
      "data": {
          "content": [
              {
                  "id": 25,
                  "username": "maj",
                  "password": "$2a$10$bO4Kp5Y.7L9b2fmpVSO3suniCScmiPj47pk.7D/yifUgz8mhm79ba",
                  "employeeId": 1001,
                  "firstName": null,
                  "lastName": null,
                  "email": null,
                  "roles": [
                      {
                          "id": 5,
                          "name": "收费员",
                          "value": "ROLE_CHARGER",
                          "authorities": [
                              {
                                  "id": 34,
                                  "name": "车辆驶入",
                                  "value": "order-order-driveIn"
                              }
                          ]
                      }
                  ],
                  "authorities": [

                      {
                          "authority": "order-order-driveIn"
                      }
                  ],
                  "enabled": true,
                  "accountNonExpired": true,
                  "credentialsNonExpired": true,
                  "accountNonLocked": true
              }
          ],
          "last": true,
          "totalPages": 1,
          "totalElements": 1,
          "number": 0,
          "size": 20,
          "numberOfElements": 1,
          "sort": null,
          "first": true
      }
  }
  ```
### 5.1.6 角色信息自动提示查询接口

- 功能描述: 根据用户名自动提示查询用户信息

- 请求地址: http://domain/uaa/sysusers/autoTop?username=USERNAME&access_token=ACCESS_TOKEN

- 请求动作: GET

- 请求示例: http://domain/uaa/sysusers/autoTop?username=maj&access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca

- 返回数据示例  
  ```
  {
      "status": "SUCCESS",
      "data": [
          {
              "id": 25,
              "username": "maj",
              "password": "$2a$10$bO4Kp5Y.7L9b2fmpVSO3suniCScmiPj47pk.7D/yifUgz8mhm79ba",
              "employeeId": 1001,
              "firstName": null,
              "lastName": null,
              "email": null,
              "authorities": [
                  {
                      "authority": "billing-monthBill-save"
                  },
                  {
                      "authority": "billing-chargingStrategy-save"
                  }
              ],
              "enabled": true,
              "credentialsNonExpired": true,
              "accountNonLocked": true,
              "accountNonExpired": true
          }
      ]
  }

  ```
 ### 5.1.7 重置密码接口

- 功能描述: 重置密码
- 请求地址: `http://domain/uaa/sysusers/reset/{id}?access_token=ACCESS_TOKEN`
- 请求动作: `PUT`
- 请求示例: `http://domain/uaa/sysusers/reset/1002?access_token=5d780ca8-fc23-4bfd-8513-d64b517e9d63`
- 返回示例：
 ```
 {
     "status": "SUCCESS",
     "data": "重置密码成功"
 }
 
 ```

 ### 5.1.8 修改密码接口

-   功能描述: 修改密码
  - 请求地址: `http://domain/uaa/sysusers/modifyPwd?access_token=ACCESS_TOKEN`
  - 请求动作: `PUT`
  - 请求示例: `http://domain/uaa/sysusers/modifyPwd?access_token=5d780ca8-fc23-4bfd-8513-d64b517e9d63`
  - 请求数据示例：
  ```
  {
      "username":"999",
      "oldPassword":"123123",
      "newPassword":"123456"
  }

  ```

### 5.1.9 判断员工是否被绑定

- 功能描述: 判断员工是否被绑定

- 请求地址: `http://domain/uaa/sysusers/employees/{id}?access_token=ACCESS_TOKEN`

- 请求动作: `HEAD`

- 请求示例: `http://domain/uaa/sysusers/employees/1001?access_token=5d780ca8-fc23-4bfd-8513-d64b517e9d63`

- 返回示例
 ```
返回信息包含在Response Header中：
hasBinding:true    已绑定
hasBinding:false   未绑定
```

### 5.1.10  判断用户是否已注册

- 功能描述: 判断用户是否已注册

- 请求地址: `http://domain/uaa/sysusers/?username=a&?access_token=ACCESS_TOKEN`

- 请求动作: `HEAD`

- 请求示例: `http://domain/uaa/sysusers?username=a&access_token=5d780ca8-fc23-4bfd-8513-d64b517e9d63`

- 返回示例  
```
返回信息包含在Response Header中：
isExist:true    已存在
isExist:false   不存在
```
  ​

# 5.2 RoleController测试用例

### 5.2.1 查看角色信息接口

- 功能描述:  根据id查看角色信息
- 请求地址: `http://domain/uaa/sysroles/{id}?access_token=ACCESS_TOKEN`
- 请求动作: `GET`
- 请求示例: `http://domain/uaa/sysroles/4?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`  

- 返回数据示例
  ```
    {
    	"status": "SUCCESS",
    	"data": {
        	"id": 4,
        	"name": "普通用户",
        	"value": "ROLE_USER",
        	"authorities": []
    	}
    }
  ```

###  5.2.2 查看角色信息列表接口

- 功能描述:  查看角色信息列表
- 请求地址: `http://domain/uaa/sysroles?access_token=ACCESS_TOKEN`
- 请求动作: `GET`
- 请求示例: `http://domain/uaa/sysroles?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`  


- 返回数据示例
  ```
    {
        "status": "SUCCESS",
        "data": [
            {
                "id": 3,
                "name": "管理员",
                "value": "ROLE_ADMIN",
                "authorities": [
                    {
                        "id": 29,
                        "name": "权限信息查询",
                        "value": "auth-authority-query"
                    }
                ]
            }
        ]
    }
  ```

### 5.2.3 新建角色接口

- 功能描述:  新建角色
- 请求地址: `http://domain/uaa/sysroles?access_token=ACCESS_TOKEN`
- 请求动作: `POST`
- 请求示例: `http://domain/uaa/sysroles?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`  

- POST数据示例
  ```
    {
    	"name":"观察员",
  	"value":"ROLE_OBSERVE"
    }
  ```

### 5.2.4 更新角色信息接口

- 功能描述:  根据id更新角色信息
- 请求地址: `http://domain/uaa/sysroles/{id}?access_token=ACCESS_TOKEN`
- 请求动作: `PUT`
- 请求示例: `http://domain/uaa/sysroles/49?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`  

- PUT数据示例
  ```
    {
    	"name":"收费员2",
  	"value":"ROLE_CHARGER2"
    }
  ```

# 5.3 AuthorityController测试用例

### 5.3.1 查询权限信息接口

- 功能描述:  根据id查询权限信息
- 请求地址: `http://domain/uaa/sysauthorities/{id}?access_token=ACCESS_TOKEN`
- 请求动作: `GET`
- 请求示例: `http://domain/uaa/sysauthorities/18?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`  

- 返回数据示例
  ```
    {
    	"status": "SUCCESS",
    	"data": {
        	"id": 18,
        	"name": "查看用户列表",
        	"value": "auth-user-list"
    	}
    }
  ```

### 5.3.2 查询权限信息列表接口

- 功能描述:  查询权限信息列表
- 请求地址: `http://domain/uaa/sysauthorities?access_token=ACCESS_TOKEN`
- 请求动作: `GET`
- 请求示例: `http://domain/uaa/sysauthorities?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`  

- 返回数据示例
  ```
    {
        "status": "SUCCESS",
        "data": [   
            {
                "id": 99,
                "name": "根据姓名查找用户",
                "value": "auth-user-query"
            }
        ]
    }
  ```
# 5.4 app CustomerUserController 测试用例

### 5.4.1 APP查询用户是否存在接口

- 功能描述:  根据phoneNum查询用户是否存在
- 请求地址: `http://domain/uaa/customerUsers`
- 请求动作: `HEAD`
- 请求示例: `http://domain/uaa/customerUsers?phoneNum=12345678910`

- 返回用户示例  
```
返回信息包含在Response Header中：
isExist:true    已存在
isExist:false   不存在
```

### 5.4.2 APP获取验证码接口  

#### 5.4.2.1 APP注册时获取验证码接口 

- 功能描述:  注册时获取验证码
- 请求地址: `http://domain/uaa/customerUsers/getCodeForRegister`
- 请求动作: `GET`
- 请求示例: `http://domain/uaa/customerUsers/getCodeForRegister?phoneNum=12345678910`

- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": "发送验证码成功"
}

```

#### 5.4.2.1 APP忘记密码时获取验证码接口 

- 功能描述:  忘记密码时获取验证码
- 请求地址: `http://domain/uaa/customerUsers/getCodeForPassword`
- 请求动作: `GET`
- 请求示例: `http://domain/uaa/customerUsers/getCodeForPassword?phoneNum=12345678910`

- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": "发送验证码成功"
}

```

### 5.4.3 APP验证验证码接口  

- 功能描述:  验证验证码
- 请求地址: `http://domain/uaa/customerUsers/verifyCode`
- 请求动作: `GET`
- 请求示例: `http://domain/uaa/customerUsers/verifyCode?phoneNum=12345678910&verificationCode=402624`

- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": "验证码正确"
}

```

### 5.4.4 APP用户注册接口  

- 功能描述:  用户注册
- 请求地址: `http://domain/uaa/customerUsers`
- 请求动作: `POST`
- 请求示例: `http://domain/uaa/customerUsers`

- 请求数据示例  
```
{
	"phoneNum":"12345678910",
	"password":"111111"
}

```

### 5.4.5 APP用户忘记密码接口  

- 功能描述:  忘记密码
- 请求地址: `http://domain/uaa/customerUsers/forgetPwd`
- 请求动作: `PUT`
- 请求示例: `http://domain/uaa/customerUsers/forgetPwd`

- 请求数据示例  
```
{
	"phoneNum":"12345678910",
	"password":"111111"
}

```

### 5.4.6 APP用户修改密码接口  

- 功能描述:  修改密码
- 请求地址: `http://domain/uaa/customerUsers/modifyPwd?access_token=dq12e1ed132ed23d232d2d32d23d`
- 请求动作: `PUT`
- 请求示例: `http://domain/uaa/customerUsers/modifyPwd?access_token=dq12e1ed132ed23d232d2d32d23d`

- 请求数据示例  
```
{
	"phoneNum":"12345678910",
	"oldPassword":"111111",
	"newPassword":"123456"
}

```
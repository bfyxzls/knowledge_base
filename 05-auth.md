
## 初始获取access_token接口

- 功能描述: 获取access_token
- 请求地址: `http://domain/uaa/oauth/token`
- 请求动作: `POST`
- 请求示例: `http://domain/uaa/oauth/token?grant_type=password&username=maj&password=maj`  
      Authorization：  
      &emsp;&emsp;Type:Base Auth  
      &emsp;&emsp;Username:android  
      &emsp;&emsp;Password:android
            
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
      &emsp;&emsp;Type:Base Auth  
      &emsp;&emsp;Username:android  
      &emsp;&emsp;Password:android
            
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
                  "id": 5,
                  "username": "admin",
                  "password": "$2a$10$XOVs4Z1YtPKqKwQVywG9j.xLAqXYRQLGZMGMrZDNbtl6pUC0Weteq",
                  "employeeId": null,
                  "firstName": null,
                  "lastName": null,
                  "email": null,
                  "roles": [
                      {
                          "id": 3,
                          "name": "管理员",
                          "value": "ROLE_ADMIN",
                          "authorities": [
                              {
                                  "id": 23,
                                  "name": "查看角色列表",
                                  "value": "auth-role-list"
                              },
                              ...
                              {
                                  "id": 29,
                                  "name": "权限信息查询",
                                  "value": "auth-authority-query"
                              }
                          ]
                      }
                  ],
                  "authorities": [
                      {
                          "authority": "infras-dept-top10"
                      },
                      ...
                      {
                          "authority": "infras-parkingarea-one"
                      }
                  ],
                  "enabled": true,
                  "credentialsNonExpired": true,
                  "accountNonLocked": true,
                  "accountNonExpired": true
              },
              {
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
              },
              {
                  "id": 26,
                  "username": "lunx",
                  "password": "$2a$10$dZFlEj9zxQX3/2Ju15FUQeJV8wSrAltnqLlTGuQH5or8Jv3vmObQK",
                  "employeeId": null,
                  "firstName": null,
                  "lastName": null,
                  "email": null,
                  "roles": [],
                  "authorities": [],
                  "enabled": true,
                  "credentialsNonExpired": true,
                  "accountNonLocked": true,
                  "accountNonExpired": true
              },
          ],
          "last": true,
          "totalPages": 1,
          "totalElements": 4,
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
  	"password":"zzzzzz",
  	"employeeId": 1002,
  	"roles": [
             
          ],
      "authorities": [
              
          ]
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
  	"username":"zhang",
  	"password":"abcd",
  	"roles": [
             
          ],
      "authorities": [
              
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
                                  "id": 38,
                                  "name": "查看订单列表",
                                  "value": "order-order-list"
                              },
                              {
                                  "id": 33,
                                  "name": "查看属于岗位的泊位",
                                  "value": "order-order-allParkingsByPost"
                              },
                              {
                                  "id": 36,
                                  "name": "上传车辆图片",
                                  "value": "order-order-uploadImage"
                              },
                              {
                                  "id": 35,
                                  "name": "车辆驶出",
                                  "value": "order-order-driveOut"
                              },
                              {
                                  "id": 30,
                                  "name": "查看员工默认岗位及泊位",
                                  "value": "order-order-defaultPostParkings"
                              },
                              {
                                  "id": 32,
                                  "name": "查看同一路段的岗位",
                                  "value": "order-order-defaultPostSiblings"
                              },
                              {
                                  "id": 37,
                                  "name": "查看车辆图片",
                                  "value": "order-order-image"
                              },
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
                          "authority": "order-order-defaultPostParkings"
                      },
                      {
                          "authority": "order-order-defaultPostSiblings"
                      },
                      {
                          "authority": "order-order-list"
                      },
                      {
                          "authority": "order-order-allParkingsByPost"
                      },
                      {
                          "authority": "order-order-driveOut"
                      },
                      {
                          "authority": "order-order-image"
                      },
                      {
                          "authority": "order-order-uploadImage"
                      },
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
    	"data": {
        "content": [
            {
                "id": 3,
                "name": "管理员",
                "value": "ROLE_ADMIN",
                "authorities": [
                    {
                        "id": 23,
                        "name": "查看角色列表",
                        "value": "auth-role-list"
                    },
                    {
                        "id": 29,
                        "name": "权限信息查询",
                        "value": "auth-authority-query"
                    }
                ]
            },
            {
                "id": 4,
                "name": "普通用户",
                "value": "ROLE_USER",
                "authorities": []
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 3,
        "number": 0,
        "size": 20,
        "numberOfElements": 3,
        "sort": null,
        "first": true
    }
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
    	"data": {
        	"content": [
            	{
                	"id": 38,
                	"name": "查看订单列表",
                	"value": "order-order-list"
            	},
            	{
                	"id": 30,
                	"name": "查看员工默认岗位及泊位",
                	"value": "order-order-defaultPostParkings"
            	}
        	],
        	"last": false,
        	"totalPages": 4,
        	"totalElements": 80,
        	"number": 0,
        	"size": 20,
        	"numberOfElements": 20,
        	"sort": null,
        	"first": true
    	}
    }
  ```

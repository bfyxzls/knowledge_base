#auth-server接口文档

## 查询单个用户信息##
HTTP请求方式:GET  
URL：http://.../uaa/sysusers/{id}?access_token=ACCESS_TOKEN

**返回字段JSON示例**

    {
    	"status": "SUCCESS",
    	"data": {
    		"id": 6,
    		"username": "wyf",
    		"password": "$2a$10$WjApX3bMw1KfzckGCCOB.eXRNY61ZcwsqpNzc2yiHtjsqnS3LmXAS",
    		"firstName": null,
    		"lastName": null,
    		"email": null,
    		"imageUrl": null,
    		"roles": [
    			{
    				"id": 4,
    				"name": "普通用户",
    				"value": "ROLE_USER",
    				"authorities": [
    					{
    						"id": 19,
    						"name": "添加新用户",
   							"value": "auth-user-save"
    					},
    					{
    						"id": 20,
    						"name": "查看单个用户",
    						"value": "auth-user-one"
    					},
    					{
    						"id": 18,
    						"name": "查看用户列表",
    						"value": "auth-user-list"
    					}
    				]
    			}
    		],
    		"authorities": [
    			{
    				"authority": "auth-user-one"
    			},
    			{
    				"authority": "auth-user-save"
   				},
    			{
    				"authority": "auth-user-list"
    			}
    		]
    	}
    }

## 查询用户列表接口 ##

HTTP请求方式:GET  
URL：http://.../uaa/sysusers?access_token=ACCESS_TOKEN

**返回字段JSON示例**

	{
    	"status": "SUCCESS",
    	"data": {
       		"content": [
            {
                "id": 47,
                "username": "zhang11",
                "password": "$2a$10$nmrsF3Df1Aa0L9McqVwJke5tv5cymwENKD/4b1rqKu5tlRvhhc4vy",
                "firstName": "zh2",
                "lastName": "j22",
                "email": "12762136187@qq2.com",
                "imageUrl": "http:wd2qe",
                "roles": [],
                "authorities": []
            },
			{

			}
        ],
        	"last": true,
        	"totalPages": 1,
        	"totalElements": 6,
        	"number": 0,
        	"size": 20,
        	"numberOfElements": 6,
        	"sort": null,
        	"first": true
    }
}    



## 查看当前登录用户信息 ##

HTTP请求方式:GET  
URL：http://.../uaa/sysusers/user?access_token=ACCESS_TOKEN

**返回数据示例**

    {
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
    "details": {
    "remoteAddress": "192.168.1.22",
    "sessionId": null,
    "tokenValue": "bdfc82c8-8020-4f50-8c69-125b34594a46",
    "tokenType": "Bearer",
    "decodedDetails": null
    },
    "authenticated": true,
    "userAuthentication": {
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
    "details": {
    "grant_type": "password",
    "username": "maj"
    },
    "authenticated": true,
    "principal": {
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
    "accountNonLocked": true,
    "credentialsNonExpired": true
    },
    "credentials": null,
    "name": "maj"
    },
    "principal": {
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
    "accountNonLocked": true,
    "credentialsNonExpired": true
    },
    "oauth2Request": {
    "clientId": "android",
    "scope": [
    "xx"
    ],
    "requestParameters": {
    "grant_type": "password",
    "username": "maj"
    },
    "resourceIds": [],
    "authorities": [],
    "approved": true,
    "refresh": false,
    "redirectUri": null,
    "responseTypes": [],
    "extensions": {},
    "grantType": "password",
    "refreshTokenRequest": null
    },
    "clientOnly": false,
    "credentials": "",
    "name": "maj"
    }


## 添加新用户接口 ##

HTTP请求方式:POST  
URL：http://.../uaa/sysusers?access_token=ACCESS_TOKEN

**POST数据示例**

    {
    	"username":"abc",
    	"password":"zzzzzz",
    	"email":"abc@163.com",
    	"firstName":"z",
    	"imageUrl":"http:wdqe",
    	"lastName":"j",
    	"roles": [
       
    ],
    "authorities": [
    
    ]
    }

**返回数据示例**

    {
    	"status": "SUCCESS",
    	"data": {
    		"id": 48,
    		"username": "abc",
    		"password": "$2a$10$DSCEnkU4IHunRN2OeO33B.PScGCftaE/0bMBgvqvDj4zb78E14sn2",
    		"firstName": "z",
    		"lastName": "j",
    		"email": "abc@163.com",
    		"imageUrl": "http:wdqe",
    		"roles": [],
    		"authorities": []
    	}
    }

## 更新用户信息接口 ##

HTTP请求方式:PUT  
URL：http://.../uaa/sysusers/{id}?access_token=ACCESS_TOKEN

**PUT数据示例**

    {
    	"username":"gggg",
    	"password":"zzzzzz",
    	"email":"abc@163.com",
    	"firstName":"z",
    	"imageUrl":"http://image.png",
    	"lastName":"j",
    	"roles": [
       
    ],
    "authorities": [
    
    ]
    }

**返回数据示例**

    {
    	"status": "SUCCESS",
    	"data": {
        	"id": 48,
       		"username": "gggg",
        	"password": "zzzzzz",
        	"firstName": "z",
        	"lastName": "j",
        	"email": "abc@163.com",
        	"imageUrl": "http://image.png",
        	"roles": [],
        	"authorities": []
    	}
    }


## 查看角色信息接口 ##

HTTP请求方式:GET  
URL：http://.../uaa/sysroles/{id}?access_token=ACCESS_TOKEN

**返回数据示例**

    {
    	"status": "SUCCESS",
    	"data": {
        	"id": 4,
        	"name": "普通用户",
        	"value": "ROLE_USER",
        	"authorities": []
    	}
    }


## 查看角色信息列表接口 ##

HTTP请求方式:GET  
URL：http://.../uaa/sysroles?access_token=ACCESS_TOKEN

**返回数据示例**

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


## 新建角色接口 ##

HTTP请求方式:POST  
URL：http://.../uaa/sysroles?access_token=ACCESS_TOKEN

**POST数据示例**

    {
    	"name":"观察员",
		"value":"ROLE_OBSERVE"
    }

**返回数据示例**

    {
    	"status": "SUCCESS",
    	"data": {
        	"id": 49,
        	"name": "观察员",
        	"value": "ROLE_OBSERVE",
        	"authorities": null
    	}
    }

## 更新角色信息接口 ##

HTTP请求方式:PUT  
URL：http://.../uaa/sysroles/{id}?access_token=ACCESS_TOKEN

**PUT数据示例**

    {
    	"name":"收费员2",
		"value":"ROLE_CHARGER2"
    }

**返回数据示例**

    {
    	"status": "SUCCESS",
    	"data": {
        	"id": 49,
        	"name": "收费员2",
        	"value": "ROLE_CHARGER2",
        	"authorities": []
    	}
    }


## 条件查询角色信息接口 ##

HTTP请求方式:GET  
URL：http://.../uaa/sysroles/query?name=NAME&access_token=ACCESS_TOKEN

**返回数据示例**

    {
    	"status": "SUCCESS",
    	"data": {
        	"content": [
            	{
                	"id": 4,
                	"name": "普通用户",
                	"value": "ROLE_USER",
                	"authorities": []
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


## 查询权限信息接口 ##

HTTP请求方式:GET  
URL：http://.../uaa/sysauthorities/{id}?access_token=ACCESS_TOKEN

**返回数据示例**

    {
    	"status": "SUCCESS",
    	"data": {
        	"id": 18,
        	"name": "查看用户列表",
        	"value": "auth-user-list"
    	}
    }


## 查询权限信息列表接口 ##

HTTP请求方式:GET  
URL：http://.../uaa/sysauthorities?access_token=ACCESS_TOKEN

**返回数据示例**

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

## 条件查询权限信息接口 ##

HTTP请求方式:GET  
URL：http://.../uaa/sysauthorities/query?name=NAME&access_token=ACCESS_TOKEN

**返回数据示例**

    {
    	"status": "SUCCESS",
    	"data": {
        	"content": [
            	{
                	"id": 53,
                	"name": "保存收费策略",
                	"value": "billing-chargingStrategy-save"
            	},
            	{
                	"id": 55,
                	"name": "获取收费策略列表",
                	"value": "billing-chargingStrategy-list"
            	},
            	{
                	"id": 56,
                	"name": "查看单个收费策略",
                	"value": "billing-chargingStrategy-one"
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

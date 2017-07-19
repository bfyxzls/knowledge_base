#auth-server接口文档

## 查询单个用户信息##
HTTP请求方式:GET  
URL：http://.../uaa/sysusers/{id}?access_token=ACCESS_TOKEN

**参数说明**

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |
|  id    |         是      |        查询的用户id      |

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

**返回data用户字段说明:**

|:-------------:|:-------------:|:-------------:|
|参数名          |类型           | 描述         |
|id|Long|用户id|
|username|String|用户名|
|password|String|用户密码|
|firstname|String|名|
|lastname|String|姓|
|email|String|邮箱地址|
|imageUrl|String|图片资源路径|
|roles|JSON结构|角色信息集合|
|authority|JSON结构|权限信息集合|


**roles字段说明:**

|:-------------:|:-------------:|:-------------:|
|参数名          |类型           | 描述         |
|       id        |        Long       |      角色id        |
|      name         |     String          |      角色描述        |
|       value        |         String      |        角色名      |
|   authorities            |     JSON结构          |      权限列表        |

**authorities字段说明:**

|:-------------:|:-------------:|:-------------:|
|参数名          |类型           | 描述         |
|       id        |        Long       |      权限id        |
|      name         |     String          |      权限描述       |
|       value        |         String      |        权限名     |

**authority字段说明:**

|:-------------:|:-------------:|:-------------:|
|参数名          |类型           | 描述         |
|      authority         |     String          |      权限名        |

## 查询用户列表接口 ##

HTTP请求方式:GET  
URL：http://.../uaa/sysusers?access_token=ACCESS_TOKEN

**参数说明**

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |


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

**返回data用户列表字段说明:**

|:-------------:|:-------------:|:-------------:|
|参数名          |类型           | 描述         |
|     content          |    JSON结构           |        用户信息集合      |
|      last         |       Boolean        |              |
|     totalPages          |       Integer        |      总计页数        |
|       totalElements        |      Integer         |       总计条数       |
|      number         |       Integer        |      开始数        |
|       size        |        Integer        |       每页最大展示数       |
|       numberOfElements        |       Integer        |       基础数量       |
|      sort         |        String       |              |
|      first         |         Boolean      |              |

## 查看当前登录用户信息 ##

HTTP请求方式:GET  
URL：http://.../uaa/sysusers/user?access_token=ACCESS_TOKEN


**参数说明**

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |



## 添加新用户接口 ##

HTTP请求方式:POST  
URL：http://.../uaa/sysusers?access_token=ACCESS_TOKEN

**参数说明**

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |
|    POST数据           |      是         |       JSON数据       |

**POST数据说明**

|:-------------:|:-------------:|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |类型           |示例值       |       描述     |
|        username       |      是         |      String        |    abc         |      用户名        |
|       password         |      是         |     String         |     zzzzzz        |      用户密码         |
|        email       |        否       |      String        |      abc@163.com       |       用户邮箱        |
|       imageUrl        |      否         |       String       |        http://iamge.png     |       图片        |
|       firstName         |     否          |       String       |       a      |       名        |
|      lastName        |     否          |       String       |     c        |           姓    |
|       roles        |       是        |       JSON结构      |       [    ]      |     角色集合，传空数组          |
|       authorities       |       是        |       JSON结构       |      [    ]       |      权限集合， 传空数组       |


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

**参数说明**

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |
|id               |是               |         更新用户的id|
|    PUT数据           |      是         |       JSON数据       |

**PUT数据说明**

|:-------------:|:-------------:|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |类型           |示例值       |       描述     |
|        username       |      是         |      String        |    abc         |      用户名        |
|       password         |      是         |     String         |     zzzzzz        |      用户密码         |
|        email       |        否       |      String        |      abc@163.com       |       用户邮箱        |
|       imageUrl        |      否         |       String       |        http://iamge.png     |       图片        |
|       firstName         |     否          |       String       |       a      |       名        |
|      lastName        |     否          |       String       |     c        |           姓    |
|       roles        |       是        |       JSON结构      |       [    ]      |     角色集合，传空数组          |
|       authorities       |       是        |       JSON结构       |      [    ]       |      权限集合， 传空数组       |


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

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |
|id               |是               |         查看的角色的id|

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

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |


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

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |
|    POST数据           |      是         |       JSON数据       |


|:-------------:|:-------------:|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |类型           |示例值       |       描述     |
|       name        |        是       |    String          |       "观察员"      |      角色名         |
|        value       |       是        |       String       |      ROLE_OBSERVE      |       角色描述        |

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

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |
|    PUT数据           |      是         |       JSON数据       |


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

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |
|name|否|条件字段，为null时查询所有|

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

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |
|id|是|权限id|

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

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |


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

|:-------------:|:-------------:|:-------------:|
|参数名          |必填           |描述           |
|  access_token    |         是      |        用户授权凭证      |
|name|否|条件字段，为null时查询所有|

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

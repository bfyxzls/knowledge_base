## 13.1 优惠活动信息访问接口

### 13.1.1 save接口

- 功能描述: 创建新活动

- 请求地址: `http://domain/coupon/activities`

- 请求动作: `POST`

- 请求示例: `http://localhost:8080/coupon/activities?access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`

- 请求示例

```
{
	"name":"中秋优惠",
	"fullCouponTemplate":{
		"name":"满减券",
		"validStartDate":"2017-11-21 10:30:30",
		"validEndDate":"2017-11-25 10:30:30",
		"roadSections":[
			1001,1002
		],
		"couponRules":[
			{
				"type":"fullCouponRule",
				"useLimitAmount":5,
				"discountAmount":2,
				"maxNum":2	
			},
			{
				"type":"fullCouponRule",
				"useLimitAmount":10,
				"discountAmount":5,
				"maxNum":2	
			}
			
		]
	},
	"freeCouponTemplate":{
		"name":"免费券",
		"validStartDate":"2017-11-21 19:30:30",
		"validEndDate":"2017-11-24 12:30:30",
		"roadSections":[
			1003,1004
		],
		"couponRules":[
			{
				"type":"freeCouponRule",
				"freeHours":2,
				"maxNum":2	
			}
		]
	},
	"hourCouponTemplate":{
		"name":"小时券",
		"validStartDate":"2017-11-21 10:30:30",
		"validEndDate":"2017-11-25 10:30:30",
		"roadSections":[
			1005,1006
		],
		"couponRules":[
			{
				"type":"hourCouponRule",
				"useLimitHour":1,
				"payAmount":1,
				"maxNum":2	
			},{
				"type":"hourCouponRule",
				"useLimitHour":2,
				"payAmount":5,
				"maxNum":2	
			}
		]
	},
	"straightCutCouponTemplate":{
		"name":"直减券",
		"validStartDate":"2017-11-21 10:30:30",
		"validEndDate":"2017-11-25 10:30:30",
		"roadSections":[
			1005,1006
		],
		"couponRules":[
			{
				"type":"straightCutCouponRule",
				"discountAmount":5,
				"maxNum":1	
			},{
				"type":"straightCutCouponRule",
				"discountAmount":10,
				"maxNum":2	
			}
		]
	}
}

```

### 13.1.2 list接口

- 功能描述: 创建优惠券时，输入活动名获得活动下拉框提醒

- 请求地址: `http://localhost:8080/coupon/activities`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/coupon/activities?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 返回示例

```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": "5a13cc956c79211554a7f9ca",
                "name": "圣诞优惠",
                "status": 1,
                "fullCouponTemplate": {
                    "name": "满减券",
                    "validStartDate": "2017-11-21 10:30:30",
                    "validEndDate": "2017-11-25 10:30:30",
                    "roadSections": [
                        1001,
                        1002
                    ],
                    "couponRules": [
                        {
                            "type": "fullCouponRule",
                            "useLimitAmount": 5,
                            "discountAmount": 2,
                            "generateNum": null,
                            "maxNum": 2
                        },
                        {
                            "type": "fullCouponRule",
                            "useLimitAmount": 10,
                            "discountAmount": 5,
                            "generateNum": null,
                            "maxNum": 2
                        }
                    ]
                },
                "freeCouponTemplate": {
                    "name": "免费券",
                    "validStartDate": "2017-11-21 19:30:30",
                    "validEndDate": "2017-11-24 12:30:30",
                    "roadSections": [
                        1003,
                        1004
                    ],
                    "couponRules": [
                        {
                            "type": "freeCouponRule",
                            "freeHours": 2,
                            "generateNum": null,
                            "maxNum": 2
                        }
                    ]
                },
                "hourCouponTemplate": {
                    "name": "小时券",
                    "validStartDate": "2017-11-21 10:30:30",
                    "validEndDate": "2017-11-25 10:30:30",
                    "roadSections": [
                        1005,
                        1006
                    ],
                    "couponRules": [
                        {
                            "type": "hourCouponRule",
                            "useLimitHour": 1,
                            "payAmount": 1,
                            "generateNum": null,
                            "maxNum": 2
                        },
                        {
                            "type": "hourCouponRule",
                            "useLimitHour": 2,
                            "payAmount": 5,
                            "generateNum": null,
                            "maxNum": 2
                        }
                    ]
                },
                "straightCutCouponTemplate": {
                    "name": "直减券",
                    "validStartDate": "2017-11-21 10:30:30",
                    "validEndDate": "2017-11-25 10:30:30",
                    "roadSections": [
                        1005,
                        1006
                    ],
                    "couponRules": [
                        {
                            "type": "straightCutCouponRule",
                            "discountAmount": 5,
                            "generateNum": null,
                            "maxNum": 1
                        },
                        {
                            "type": "straightCutCouponRule",
                            "discountAmount": 10,
                            "generateNum": null,
                            "maxNum": 2
                        }
                    ]
                },
                "createdDate": "2017-11-21 14:49:57"
            }
        ]
    }
}

```
### 13.1.3 search接口

- 功能描述: 活动列表条件查询时

- 请求地址: `http://domain/coupon/activities/search`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/coupon/activities/search?name=优惠&status=&page=10&size=20&sort=createdDate,DESC&access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 返回示例

```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": "5a13cc956c79211554a7f9ca",
                "name": "圣诞优惠",
                "status": 1,
                "fullCouponTemplate": {
                    "name": "满减券",
                    "validStartDate": "2017-11-21 10:30:30",
                    "validEndDate": "2017-11-25 10:30:30",
                    "roadSections": [
                        1001,
                        1002
                    ],
                    "couponRules": [
                        {
                            "type": "fullCouponRule",
                            "useLimitAmount": 5,
                            "discountAmount": 2,
                            "generateNum": null,
                            "maxNum": 2
                        },
                        {
                            "type": "fullCouponRule",
                            "useLimitAmount": 10,
                            "discountAmount": 5,
                            "generateNum": null,
                            "maxNum": 2
                        }
                    ]
                },
                "freeCouponTemplate": {
                    "name": "免费券",
                    "validStartDate": "2017-11-21 19:30:30",
                    "validEndDate": "2017-11-24 12:30:30",
                    "roadSections": [
                        1003,
                        1004
                    ],
                    "couponRules": [
                        {
                            "type": "freeCouponRule",
                            "freeHours": 2,
                            "generateNum": null,
                            "maxNum": 2
                        }
                    ]
                },
                "hourCouponTemplate": {
                    "name": "小时券",
                    "validStartDate": "2017-11-21 10:30:30",
                    "validEndDate": "2017-11-25 10:30:30",
                    "roadSections": [
                        1005,
                        1006
                    ],
                    "couponRules": [
                        {
                            "type": "hourCouponRule",
                            "useLimitHour": 1,
                            "payAmount": 1,
                            "generateNum": null,
                            "maxNum": 2
                        },
                        {
                            "type": "hourCouponRule",
                            "useLimitHour": 2,
                            "payAmount": 5,
                            "generateNum": null,
                            "maxNum": 2
                        }
                    ]
                },
                "straightCutCouponTemplate": {
                    "name": "直减券",
                    "validStartDate": "2017-11-21 10:30:30",
                    "validEndDate": "2017-11-25 10:30:30",
                    "roadSections": [
                        1005,
                        1006
                    ],
                    "couponRules": [
                        {
                            "type": "straightCutCouponRule",
                            "discountAmount": 5,
                            "generateNum": null,
                            "maxNum": 1
                        },
                        {
                            "type": "straightCutCouponRule",
                            "discountAmount": 10,
                            "generateNum": null,
                            "maxNum": 2
                        }
                    ]
                },
                "createdDate": "2017-11-21 14:49:57"
            }
        ],
        "totalElements": 6,
        "totalPages": 2,
        "last": true,
        "number": 1,
        "size": 4,
        "sort": [
            {
                "direction": "DESC",
                "property": "createdDate",
                "ignoreCase": false,
                "nullHandling": "NATIVE",
                "ascending": false,
                "descending": true
            }
        ],
        "first": false,
        "numberOfElements": 2
    }
}

```


## 13.2 优惠券信息访问接口


### 13.2.1 web端新增优惠券接口

- 功能描述: 新增优惠券

- 请求地址: `http://domain/coupon/coupons`

- 请求动作: `POST`

- 请求示例: `http://localhost:8080/coupon/coupons?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 请求示例

```
 {
  "activity":{
   "id":"5a13cc956c79211554a7f9ca",
   "name":"圣诞优惠"
  },
  "fullCouponTemplate":{
   "name":"满减券",
   "validStartDate":"2017-11-21 10:30:30",
   "validEndDate":"2017-11-24 10:30:30",
   "roadSections":[
    1001,1002
   ],
   "couponRules":[
    {
     "type":"fullCouponRule",
     "useLimitAmount":5,
     "discountAmount":2,
     "maxNum":2,
     "generateNum":5
    },
    {
     "type":"fullCouponRule",
     "useLimitAmount":10,
     "discountAmount":5,
     "maxNum":2,
     "generateNum":5 
    }
    
   ]
  },
  "freeCouponTemplate":{
   "name":"免费券",
   "validStartDate":"2017-11-21 19:30:30",
   "validEndDate":"2017-11-24 12:30:30",
   "roadSections":[
    1003,1004
   ],
   "couponRules":[
    {
     "type":"freeCouponRule",
     "freeHours":2,
     "maxNum":2,
     "generateNum":5 
    }
   ]
  },
  "hourCouponTemplate":{
   "name":"小时券",
   "validStartDate":"2017-11-21 10:30:30",
   "validEndDate":"2017-11-24 10:30:30",
   "roadSections":[
    1005,1006
   ],
   "couponRules":[
    {
     "type":"hourCouponRule",
     "useLimitHour":1,
     "payAmount":1,
     "maxNum":2,
     "generateNum":5 
    },{
     "type":"hourCouponRule",
     "useLimitHour":2,
     "payAmount":5,
     "maxNum":2,
     "generateNum":5 
    }
   ]
  },
  "straightCutCouponTemplate":{
   "name":"直减券",
   "validStartDate":"2017-11-21 10:30:30",
   "validEndDate":"2017-11-24 10:30:30",
   "roadSections":[
    1005,1006
   ],
   "couponRules":[
    {
     "type":"straightCutCouponRule",
     "discountAmount":5,
     "maxNum":1,
     "generateNum":5
    },{
     "type":"straightCutCouponRule",
     "discountAmount":10,
     "maxNum":2,
     "generateNum":5
    }
   ]
  },
  "phoneNums":[],
  "assignable":true
 }


```

### 13.2.2 web端查询优惠券接口

- 功能描述: 根据券号模糊匹配，类型，归属活动，状态查找符合条件的优惠券

- 请求地址: `http://domain/coupon/coupons`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/coupon/coupons?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&id=1&type=1&activity.id=5a13cc956c79211554a7f9ca&activity.name=圣诞优惠&status=1&assignable=true&page=4&size=2`

- 返回示例

```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": "4fd4b0c1-a6f2-4e5f-934d-d9e25b0a5c59",
                "activityName": "圣诞优惠",
                "type": 1,
                "creator": null,
                "createDate": "2017-11-28 14:42:33",
                "validStartDate": "2017-11-21 19:30:30",
                "validEndDate": "2017-11-24 12:30:30",
                "status": 1,
                "phoneNum": null,
                "origin": null,
                "assignable": true
            },
            {
                "id": "72d04cf8-6ffa-4f14-b3a1-5eed674544cb",
                "activityName": "圣诞优惠",
                "type": 1,
                "creator": null,
                "createDate": "2017-11-28 14:42:33",
                "validStartDate": "2017-11-21 19:30:30",
                "validEndDate": "2017-11-24 12:30:30",
                "status": 1,
                "phoneNum": null,
                "origin": null,
                "assignable": true
            },
            {
                "id": "b98b1d7c-6433-4b99-9c4b-72b9ca0da6a9",
                "activityName": "圣诞优惠",
                "type": 1,
                "creator": null,
                "createDate": "2017-11-28 14:42:33",
                "validStartDate": "2017-11-21 19:30:30",
                "validEndDate": "2017-11-24 12:30:30",
                "status": 1,
                "phoneNum": null,
                "origin": null,
                "assignable": true
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 3,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 3
    }
}
```


## 13.3 APP端优惠券访问接口


### 13.3.1 app用户领取优惠券接口

- 功能描述: 领取优惠券

- 请求地址: `http://domain/coupon/coupons/acquire`

- 请求动作: `PUT`

- 请求示例: `http://localhost:8080/coupon/coupons/acquire?access_token=10371f15-09c6-48de-9770-71603781a7f8`

- 请求示例

```
领取满减券：

{
	"activity":{
	"id":"5a13cc956c79211554a7f9ca",
	 "name":"圣诞优惠"
	},
	"couponRules":[
   {
    "type":"fullCouponRule",
    "useLimitAmount":5,
    "discountAmount":2,
    "maxNum":2,
    "generateNum":5
   }
   ],
   "phoneNum":"18365265123"
}

领取免费券：
{
	"activity":{
	"id":"5a1e1543e8452f12ec522c73",
	 "name":"停车活动"
	},
	"couponRules":[
   {
    "type": "freeCouponRule",
    "freeHours": 2,
    "generateNum": 10,
    "maxNum": 2
  }
   ],
   "phoneNum":"18365265125"
}

领取小时券：
{
	"activity":{
	"id":"5a1e1543e8452f12ec522c73",
	 "name":"停车活动"
	},
	"couponRules":[
   {
     "type": "hourCouponRule",
     "useLimitHour": 1,
     "payAmount": 1,
     "generateNum": 10,
     "maxNum": 2
  }
   ],
   "phoneNum":"18365265126"
}

领取直减券：
{
	"activity":{
	"id":"5a1e1543e8452f12ec522c73",
	 "name":"停车活动"
	},
	"couponRules":[
   {
     "type": "straightCutCouponRule",
     "discountAmount": 5,
     "generateNum": 10,
     "maxNum": 1
  }
   ],
   "phoneNum":"18365265128"
}
```


### 13.3.2 app用户查看已领取的优惠券接口

- 功能描述: app用户查看优惠券

- 请求地址: `http://domain/customer/coupons/search`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/customer/coupons/search?access_token=10371f15-09c6-48de-9770-71603781a7f8&status=2`

- 返回示例

```
status=2 未使用的优惠券：
status=3:已使用的优惠券：
status=4:已失效的优惠券：

{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": "0eba4bc1-fa6d-448c-a277-2a9e0248e5e8",
                "activityName": "停车活动",
                "template": {
                    "validStartDate": 1511263830000,
                    "validEndDate": 1514687430000,
                    "roadSections": [
                        1003,
                        1004
                    ]
                },
                "rule": {
                    "type": 1,
                    "freeHours": 2,
                    "generateNum": 10,
                    "maxNum": 2
                },
                "status": 2
            },
            {
                "id": "5cab3fe3-1a1c-4c6d-b5c7-76d7d2c5121c",
                "activityName": "停车活动",
                "template": {
                    "validStartDate": 1511263830000,
                    "validEndDate": 1514687430000,
                    "roadSections": [
                        1003,
                        1004
                    ]
                },
                "rule": {
                    "type": 1,
                    "freeHours": 2,
                    "generateNum": 10,
                    "maxNum": 2
                },
                "status": 2
            },
            {
                "id": "6b821271-7242-4071-bbc1-c5480db765ab",
                "activityName": "圣诞优惠",
                "template": {
                    "validStartDate": 1511263830000,
                    "validEndDate": 1511497830000,
                    "roadSections": [
                        1003,
                        1004
                    ]
                },
                "rule": {
                    "type": 1,
                    "freeHours": 2,
                    "generateNum": 10,
                    "maxNum": 2
                },
                "status": 2
            },
            {
                "id": "e7ca84ce-84ca-423e-99ff-c37716746d77",
                "activityName": "圣诞优惠",
                "template": {
                    "validStartDate": 1511263830000,
                    "validEndDate": 1511497830000,
                    "roadSections": [
                        1003,
                        1004
                    ]
                },
                "rule": {
                    "type": 1,
                    "freeHours": 2,
                    "generateNum": 10,
                    "maxNum": 2
                },
                "status": 2
            },
            {
                "id": "9df5c187-a0e3-4c57-a2fb-a27e38aac552",
                "activityName": "圣诞优惠",
                "template": {
                    "validStartDate": 1511231430000,
                    "validEndDate": 1511577030000,
                    "roadSections": [
                        1001,
                        1002
                    ]
                },
                "rule": {
                    "type": 2,
                    "useLimitAmount": 5,
                    "discountAmount": 2,
                    "generateNum": 10,
                    "maxNum": 2
                },
                "status": 2
            },
            {
                "id": "afff09b9-c64d-40eb-b963-21a3d5263a06",
                "activityName": "圣诞优惠",
                "template": {
                    "validStartDate": 1511231430000,
                    "validEndDate": 1511577030000,
                    "roadSections": [
                        1001,
                        1002
                    ]
                },
                "rule": {
                    "type": 2,
                    "useLimitAmount": 5,
                    "discountAmount": 2,
                    "generateNum": 10,
                    "maxNum": 2
                },
                "status": 2
            },
            {
                "id": "96e12f1d-db2a-4b26-9bfc-e204253527aa",
                "activityName": "圣诞优惠",
                "template": {
                    "validStartDate": 1511231430000,
                    "validEndDate": 1511577030000,
                    "roadSections": [
                        1001,
                        1002
                    ]
                },
                "rule": {
                    "type": 2,
                    "useLimitAmount": 10,
                    "discountAmount": 5,
                    "generateNum": 10,
                    "maxNum": 2
                },
                "status": 2
            },
            {
                "id": "fcebf712-6dbf-40bc-855c-6f5f87d14e7b",
                "activityName": "圣诞优惠",
                "template": {
                    "validStartDate": 1511231430000,
                    "validEndDate": 1511577030000,
                    "roadSections": [
                        1001,
                        1002
                    ]
                },
                "rule": {
                    "type": 2,
                    "useLimitAmount": 10,
                    "discountAmount": 5,
                    "generateNum": 10,
                    "maxNum": 2
                },
                "status": 2
            }
        ],
        "totalElements": 8,
        "last": true,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 8
    }
}
```



### 13.3.3 app用户驶离结算时查看优惠券接口

- 功能描述: app用户驶离时根据路段查询当前可用的优惠券列表

- 请求地址: `http://domain/customer/coupons/obtainAvailableCoupons`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/customer/coupons/obtainAvailableCoupons?access_token=10371f15-09c6-48de-9770-71603781a7f8&roadSectionId=1001`

- 返回示例

```
   {
       "status": "SUCCESS",
       "data": [
           {
               "id": "9df5c187-a0e3-4c57-a2fb-a27e38aac552",
               "activityName": "圣诞优惠",
               "template": {
                   "validStartDate": 1511231430000,
                   "validEndDate": 1511577030000,
                   "roadSections": [
                       1001,
                       1002
                   ]
               },
               "rule": {
                   "type": 2,
                   "useLimitAmount": 5,
                   "discountAmount": 2,
                   "generateNum": 10,
                   "maxNum": 2
               },
               "status": 2
           },
           {
               "id": "afff09b9-c64d-40eb-b963-21a3d5263a06",
               "activityName": "圣诞优惠",
               "template": {
                   "validStartDate": 1511231430000,
                   "validEndDate": 1511577030000,
                   "roadSections": [
                       1001,
                       1002
                   ]
               },
               "rule": {
                   "type": 2,
                   "useLimitAmount": 5,
                   "discountAmount": 2,
                   "generateNum": 10,
                   "maxNum": 2
               },
               "status": 2
           },
           {
               "id": "96e12f1d-db2a-4b26-9bfc-e204253527aa",
               "activityName": "圣诞优惠",
               "template": {
                   "validStartDate": 1511231430000,
                   "validEndDate": 1511577030000,
                   "roadSections": [
                       1001,
                       1002
                   ]
               },
               "rule": {
                   "type": 2,
                   "useLimitAmount": 10,
                   "discountAmount": 5,
                   "generateNum": 10,
                   "maxNum": 2
               },
               "status": 2
           },
           {
               "id": "fcebf712-6dbf-40bc-855c-6f5f87d14e7b",
               "activityName": "圣诞优惠",
               "template": {
                   "validStartDate": 1511231430000,
                   "validEndDate": 1511577030000,
                   "roadSections": [
                       1001,
                       1002
                   ]
               },
               "rule": {
                   "type": 2,
                   "useLimitAmount": 10,
                   "discountAmount": 5,
                   "generateNum": 10,
                   "maxNum": 2
               },
               "status": 2
           }
       ]
   }
```

## 13.4 APP端优惠券结算访问接口

### 13.4.1 app自主驶出结算订单时，计算使用优惠券后的订单金额

- 功能描述: 计算优惠券金额

- 请求地址: `http://domain/billing/chargingStrategies/couponFee`

- 请求动作: `PUT`

- 请求示例: `http://http://localhost:8080/billing/chargingStrategies/couponFee?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&chargingStrategyId=1000&startTime=2017-11-28 7:00:00&vehicleType=02`

- 请求示例

```
满减券结算：

{
 "type":"fullCouponRule",
 "useLimitAmount":5,
  "discountAmount":2
}

小时券结算：

{
 "type":"hourCouponRule",
  "useLimitHour": 2,
  "payAmount": 5
}

免费券计算：

{
 "type":"freeCouponRule",
  "freeHours": 2
}

直减券计算：
{
  "type": "straightCutCouponRule",
  "discountAmount": 5
}




```
## 13.5 CouponRule规则

### 13.5.1 免费券FreeCouponRule

         generateNum; //生成张数
         maxNum; // 每人最多发放张数
         
         freeHours; // 免费时长
         CouponType：Integer FREE = 1;//优惠券类型
         
         例子：freeHours：2  免费停车两个小时，两小时内不收费

### 13.5.2 满减券FullCouponRule

         generateNum; //生成张数
         maxNum; // 每人最多发放张数
         
         useLimitAmount; // 金额使用限制
         discountAmount; // 优惠金额
         CouponType：Integer FULL = 3;//优惠券类型
         
         例子：useLimitAmount：20  discountAmount：5   停车金额满20分减5分
         
         
### 13.5.3 小时券HourCouponRule

         generateNum; //生成张数
         maxNum; // 每人最多发放张数
         
         useLimitHour; // 时长使用限制
         payAmount; // 实付金额
         CouponType：Integer HOUR = 2//优惠券类型
         
         例子：useLimitHour：2  payAmount：5   停车时长2小时收费5分
         
### 13.5.4 直减券StraightCutCouponRule
         
         generateNum; //生成张数
         maxNum; // 每人最多发放张数
         
         discountAmount; // 优惠金额
         CouponType：Integer STRAIGHT = 4;//优惠券类型
         
         例子：discountAmount：5   5元直减券直接优惠5分
               
         






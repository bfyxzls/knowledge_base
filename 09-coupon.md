## 9.1 优惠券信息访问接口

### 9.1.1 isActivityExistAccordingName接口

- 功能描述: 根据活动名称查找该活动时候已存在

- 请求地址: `http://domain/coupon/activities`

- 请求动作: `HEAD`

- 请求示例: `http://localhost:8080/coupon/activities?access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`

- 返回示例

```
返回信息包含在Response Header中：
isExist:true    已存在
isExist:false   不存在
```

### 9.1.2 create接口

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

### 9.1.3 autoTop接口

- 功能描述: 创建优惠券时，输入活动名获得活动下拉框提醒

- 请求地址: `http://localhost:8080/coupon/activities/autoTop`

- 请求动作: `GET`

- 请求示例: `localhost:8080/coupon/activities/autoTop?name=优惠&access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 返回示例

```

{
    "status": "SUCCESS",
    "data": [
        {
            "id": "5a139a2e6c79212bb082ec5b",
            "name": "元旦优惠"
        },
        {
            "id": "5a13cc956c79211554a7f9ca",
            "name": "圣诞优惠"
        },
        {
            "id": "5a13ccb66c79211554a7f9cb",
            "name": "新年优惠"
        },
        {
            "id": "5a13ccc56c79211554a7f9cc",
            "name": "春节优惠"
        },
        {
            "id": "5a13ccd36c79211554a7f9cd",
            "name": "五一优惠"
        },
        {
            "id": "5a13ccdf6c79211554a7f9ce",
            "name": "国庆优惠"
        },
        {
            "id": "5a13da596c7921342cf60c61",
            "name": "中秋优惠"
        }
    ]
}
```
### 9.1.3 search接口

- 功能描述: 活动列表条件查询时

- 请求地址: `http://domain/coupon/activities/search`

- 请求动作: `GET`

- 请求示例: `localhost:8080/coupon/activities/search?name=优惠&status=&page=10&size=20&sort=createdDate,DESC&access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

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

## 16.1 商业停车场信息访问接口

### 16.1.1 新增商业停车场接口

- 功能描述:  新增商业停车场
- 请求地址: `http://domain/guidance/bizParkingAreas`
- 请求动作: `POST`
- 请求示例: `http://domain/guidance/bizParkingAreas?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
- 请求示例
```
{
    "name":"二级诱导屏天河河大厦",
    "code":"111111",
    "types":[1],
    "chargeable":true,
    "district":"包河区",
    "address": "潜山路",
    "coordinate": {
            "type": "Point",
            "coordinates": [
                12,
                67
            ]
        },
    "maintainer":"李冲",
    "maintainerPhoneNum":"18756578763",
    "parkingPositionQuantity":300,
    "source":1,  //数据来源，1：老系统上报，2是捷顺，3是摄像头上报
    "province":"",
    "isOwnBusiness":false,
    "city":"",
    "unitPrice":0,
    "openingHour":"7:00-22:00",
    "tags":[],
    "bizParkingAreaType":1 
}
```

- 返回示例
```
{
    "status": "SUCCESS",
    "data": "停车场信息创建成功"
}
```


### 16.1.2 更新商业停车场接口

- 功能描述:  更新商业停车场
- 请求地址: `http://domain/guidance/bizParkingAreas/20`
- 请求动作: `PUT`
- 请求示例: `http://domain/guidance/bizParkingAreas/20?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
- 请求示例
```
{
    "name":"二级诱导屏天河河大厦",
    "code":"111111",
    "types":[1],
    "chargeable":true,
    "district":"包河区",
    "address": "潜山路",
    "coordinate": {
            "type": "Point",
            "coordinates": [
                12,
                67
            ]
        },
    "maintainer":"李冲",
    "maintainerPhoneNum":"18756578763",
    "parkingPositionQuantity":300,
    "source":1,  //数据来源，1：老系统上报，2是捷顺，3是摄像头上报
    "province":"",
    "city":"",
    "isOwnBusiness":false,
    "unitPrice":0,
    "tags":[],
    "bizParkingAreaType":1
}
```

- 返回示例
```
{
    "status": "SUCCESS",
    "data": "停车场信息更新成功"
}
```


### 16.1.3 web端获取商业停车场详情接口

- 功能描述:  获取商业停车场详情
- 请求地址: `http://domain/guidance/bizParkingAreas/15`
- 请求动作: `GET`
- 请求示例: `http://domain/guidance/bizParkingAreas/15?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`


- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 15,
        "name": "二级诱导屏天河河大厦",
        "code": "111111",
        "types": [
            1
        ],
        "chargeable": true,
        "district": "包河区",
        "address": "潜山路",
        "coordinate": "11,11",
        "maintainer": "李冲",
        "maintainerPhoneNum": "18756578763",
        "parkingPositionQuantity":300,
        "source":1,  //数据来源，1：老系统上报，2是捷顺，3是摄像头上报
        "province":"",
        "city":"",
        "isOwnBusiness":false,
        "unitPrice":0,
        "bizParkingAreaType":1,
        "tags":[],
        "openingHour":"7:00-22:00"
   
    }
}
```

### 16.1.4 条件查询商业停车场接口

- 功能描述:  条件查询商业停车场
- 请求地址: `http://domain/guidance/bizParkingAreas/query`
- 请求动作: `GET`
- 请求示例: `http://domain/guidance/bizParkingAreas/query?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&name=诱导&code=111&page=0&size=10&sort`


- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 14,
                "name": "一级诱导屏银河大厦",
                "code": "111111",
                "types": [
                    1
                ],
                "chargeable": true,
                "district": "包河区",
                "address": "潜山路",
                "coordinate": "11,11",
                "maintainer": "李冲",
                "maintainerPhoneNum": "18756578763",
                "parkingPositionQuantity":300,
                "source":1,  //数据来源，1：老系统上报，2是捷顺，3是摄像头上报
                "province":"",
                "city":"",
                "isOwnBusiness":false,
                "unitPrice":0,
            },
            {
                "id": 15,
                "name": "二级诱导屏天河河大厦",
                "code": "111111",
                "types": [
                    1
                ],
                "chargeable": true,
                "district": "包河区",
                "address": "潜山路",
                "coordinate": {
                        "type": "Point",
                        "coordinates": [
                            12,
                            67
                        ]
                    },
                "maintainer": "李冲",
                "maintainerPhoneNum": "18756578763",
                "parkingPositionQuantity":300,
                "source":1,  //数据来源，1：老系统上报，2是捷顺，3是摄像头上报
                "province":"",
                "city":"",
                "isOwnBusiness":false,
                "unitPrice":0,
            }
        ],
        "last": true,
        "totalElements": 2,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 2
    }
}
```

### 16.1.5 新建诱导预案时下拉无停车预案的停车场列表接口

- 功能描述:  获取无停车预案的停车场列表
- 请求地址: `http://domain/guidance/bizParkingAreas/unrelated`
- 请求动作: `GET`
- 请求示例: `http://domain/guidance/bizParkingAreas/unrelated?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&name=路`


- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "name": "二级诱导屏天河河大厦",
            "id": 15
        }
    ]
}
```

### 16.1.6 商业停车场唯一性验证接口 
- 功能描述:  根据code查询停车场是否存在
- 请求地址: `http://localhost:8080/guidance/bizParkingAreas?access_token=5709e4d3-49d1-4499-89c4-76905af9e87c&code=154146`
- 请求动作: `HEAD`
- 请求示例: `http://localhost:8080/guidance/bizParkingAreas?access_token=5709e4d3-49d1-4499-89c4-76905af9e87c&code=154146`

- 返回用户示例  
```
返回信息包含在Response Header中：
isExist:true    已存在
isExist:false   不存在
```

### 16.1.7 地图上查看所有商业停车场坐标信息接口

- 功能描述:  地图上查看所有商业停车场坐标信息
- 请求地址: `http://domain/guidance/bizParkingAreas/coordinates`
- 请求动作: `GET`
- 请求示例: `http://domain/guidance/bizParkingAreas/coordinates?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`


- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 15,
            "coordinate": {
                "type": "Point",
                "coordinates": [
                    12,
                    67
                ]
            }
        }
    ]
}
```
### 16.1.8 查询未关联led的停车场

- 功能描述:  查询未关联led的停车场
- 请求地址: `http://localhost:8080/guidance/bizParkingAreas/unrelatedLed`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/guidance/bizParkingAreas/unrelatedLed?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&id=`
- 返回示例
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 91,
            "name": "二级诱导屏天河河大厦"
        },
        {
            "id": 92,
            "name": "二级诱导屏天河河大厦"
        },
        {
            "id": 99,
            "name": "二级诱导屏天河河大厦"
        }
    ]
}

### 16.1.9 app端获取商业停车场信息

- 功能描述:  app端获取停车场信息
- 请求地址: `http://domain/guidance/app/bizParkingAreas/{id}`
- 请求动作: `GET`
- 请求示例: `http://domain/guidance/app/bizParkingAreas/112?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
- 返回示例：


{
    "status": "SUCCESS",
    "data": {
        "id": 139,
        "name": "测试停车场3",
        "bizParkingAreaType": 1,
        "address": "潜山路",
        "tags": [
            "在线缴费",
            "24小时"
        ],
        "firstHourPrice": 3,
        "parkingRemainNum": 12,
        "openingHour": "7:00-20:00",
        "bizParkingAreaChargeDtos": [
            {
                "fee": 0,
                "hour": "15分钟"
            },
            {
                "fee": 5,
                "hour": "1小时"
            },
            {
                "fee": 7,
                "hour": "3小时"
            },
            {
                "fee": 9,
                "hour": "5小时"
            },
            {
                "fee": 10,
                "hour": "封顶"
            }
        ]
    }
}


### 16.1.10 
- 功能描述： app端根据中心坐标获取一定范围内的停车场
- 请求地址: `http://domain/guidance/app/bizParkingAreas?access_token=ba7901a0-e3c1-44ca-96c5-b2dddd6da3e1`
- 请求动作: `POST`
- 请求示例: `http://domain/guidance/app/bizParkingAreas?access_token=ba7901a0-e3c1-44ca-96c5-b2dddd6da3e1`
```json
{"type":"Point", "coordinates":[12,67.0001]}
```
- 返回示例：
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 139,
            "name": "测试停车场3",
            "address": "潜山路",
            "distance": 10,
            "unitPrice": 3,
            "remainParkingNum": null,
            "geometry": {
                "type": "Point",
                "coordinates": [
                    12,
                    67
                ]
            }
        },
        {
            "id": 140,
            "name": "测试停车场3",
            "address": "潜山路",
            "distance": 10,
            "unitPrice": 3,
            "remainParkingNum": null,
            "geometry": {
                "type": "Point",
                "coordinates": [
                    12,
                    67
                ]
            }
        },
        {
            "id": 112,
            "name": "修改后测试停车场88888",
            "address": "潜山路",
            "distance": 10,
            "unitPrice": 10,
            "remainParkingNum": null,
            "geometry": {
                "type": "Point",
                "coordinates": [
                    12,
                    67
                ]
            }
        },
        {
            "id": 162,
            "name": "二级诱导屏天河河大厦",
            "address": "潜山路",
            "distance": 10,
            "unitPrice": 0,
            "remainParkingNum": null,
            "geometry": {
                "type": "Point",
                "coordinates": [
                    12,
                    67
                ]
            }
        },
        {
            "id": 137,
            "name": "测试停车场2",
            "address": "潜山路",
            "distance": 10,
            "unitPrice": 3,
            "remainParkingNum": 105,
            "geometry": {
                "type": "Point",
                "coordinates": [
                    12,
                    67
                ]
            }
        }
    ]
}
```

### 16.1.11 获取剩余车位数
- 功能描述： 获取剩余车位数
- 请求地址: `http://domain/guidance/bizParkingAreas/remainParkingNum?access_token=ba7901a0-e3c1-44ca-96c5-b2dddd6da3e1&code=CODE`
- 请求动作: `GET`
- 请求示例: `http://domain/guidance/bizParkingAreas/remainParkingNum?access_token=ba7901a0-e3c1-44ca-96c5-b2dddd6da3e1&code=000820`

- 返回示例：
```
{
    "status": "SUCCESS",
    "data": 10
}

```


## 16.2 诱导预案访问接口

### 16.2.1 新增诱导预案接口

- 功能描述:  新增诱导预案
- 请求地址: `http://domain/guidance/inductionPlans`
- 请求动作: `POST`
- 请求示例: `http://domain/guidance/inductionPlans?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
      - 请求示例
```
{
	"num":30,
	"type":1,  //  1:+ 0:-
	"week":[
	  1,2,3	
	],
	"startTime": "9:00:00",
	"endTime":"17:00:00",
	"validStartDate":"2017-12-20",
	"validEndDate":"2017-12-25",
	"bizParkingAreaId": 6
}
```

- 返回示例
```
{
    "status": "SUCCESS",
    "data": "诱导预案信息创建成功"
}
```


### 16.2.2 更新诱导预案接口

- 功能描述:  更新诱导预案
- 请求地址: `http://domain/guidance/inductionPlans/13`
- 请求动作: `PUT`
- 请求示例: `http://domain/guidance/inductionPlans/13?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
- 请求示例
```
{
	"num":20,
	"type":0,
	"week":[
	  1,2,3,4
	],
	"startTime": "10:00:00",
	"endTime":"17:00:00",
	"validStartDate":"2017-12-20",
	"validEndDate":"2017-12-25",
	"bizParkingAreaId":113
}
```

- 返回示例
```
{
    "status": "SUCCESS",
    "data": "诱导预案信息更新成功"
}
```


### 16.2.3 获取诱导预案详情接口

- 功能描述:  获取诱导预案详情
- 请求地址: `http://domain/guidance/inductionPlans/15`
- 请求动作: `GET`
- 请求示例: `http://domain/guidance/inductionPlans/15?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`


- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "bizParkingAreaName": "一级诱导屏银河大厦",
        "num": 30,
        "type": 1,
        "week": [
            1,
            2,
            3
        ],
        "startTime": "10:00:00",
        "endTime": "17:00:00",
        "validStartDate": "2017-12-20",
        "validEndDate": "2017-12-25"
    }
}
```

### 16.2.4 条件查询诱导预案接口

- 功能描述:  条件查询诱导预案
- 请求地址: `http://domain/guidance/inductionPlans/query`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/guidance/inductionPlans/query?access_token=446d1530-2ebb-4504-ab17-dae459465d63&bizParkingAreaName=诱导&page=0&size=10&sort`


- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "bizParkingAreaName": "一级诱导屏银河大厦",
                "num": 20,
                "type": 0,
                "week": [
                    1,
                    2,
                    3,
                    4
                ],
                "startTime": "10:00:00",
                "endTime": "17:00:00",
                "validStartDate": "2017-12-20",
                "validEndDate": "2017-12-25"
            },
            {
                "bizParkingAreaName": "二级诱导屏天河河大厦",
                "num": 30,
                "type": 1,
                "week": [
                    1,
                    2,
                    3
                ],
                "startTime": "10:00:00",
                "endTime": "17:00:00",
                "validStartDate": "2017-12-20",
                "validEndDate": "2017-12-25"
            }
        ],
        "last": true,
        "totalElements": 2,
        "totalPages": 1,
        "number": 0,
        "size": 10,
        "sort": null,
        "first": true,
        "numberOfElements": 2
    }
}
```


## 16.3 诱导屏访问接口

### 16.3.1 新增诱导屏接口

- 功能描述:  新增诱导屏
- 请求地址: `http://domain/guidance/screens`
- 请求动作: `POST`
- 请求示例: `http://domain/guidance/screens?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
- 请求示例
```

novaId: NotNull!

{
	"name":"长江西路诱导牌",
	"level":1,
	"novaId":1,
	"ledIds": [
		1,2,3,4
	],
	"district":"庐阳区",
	"address":"贵潜路口",
	"coordinate": {
            "type": "Point",
            "coordinates": [
                12,
                67
            ]
        }
}
```

- 返回示例
```
{
    "status": "SUCCESS",
    "data": "诱导屏信息创建成功"
}
```


### 16.3.2 更新诱导屏接口

- 功能描述:  更新诱导屏
- 请求地址: `http://domain/guidance/screens/20`
- 请求动作: `PUT`
- 请求示例: `http://domain/guidance/screens/20?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
- 请求示例
```
{
	"name":"长江西路诱导牌",
	"level":2,
	"novaId":1,
	"ledIds": [
		1,2,4
	],
	"district":"蜀山阳区",
	"address":"明珠广场",
	"coordinate": {
            "type": "Point",
            "coordinates": [
                12,
                67
            ]
        }
}
```

- 返回示例
```
{
    "status": "SUCCESS",
    "data": "诱导屏信息更新成功"
}
```


### 16.3.3 获取诱导屏详情接口

- 功能描述:  获取诱导屏
- 请求地址: `http://domain/guidance/screens/15`
- 请求动作: `GET`
- 请求示例: `http://domain/guidance/screens/102?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`


- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 102,
        "name": "长江西路诱导牌1222",
        "district": "庐阳区",
        "coordinate": {
            "type": "Point",
            "coordinates": [
                12,
                67
            ]
        },
        "address": "贵潜路口",
        "level": 1,
        "maintainer": null,
        "maintainerPhoneNum": null,
        "screenLedDtos": [
            {
                "id": 98,
                "name": "led测试12",
                "index": 1
            },
            {
                "id": 100,
                "name": "修改后的LED",
                "index": 2
            }
        ],
        "novaCode": "54321",
        "novaId": 54321
    }
}
```


### 16.3.4 条件查询诱导屏接口

- 功能描述:  条件查询诱导屏
- 请求地址: `http://domain/guidance/screens/query`
- 请求动作: `GET`
- 请求示例: `http://domain/guidance/screens/query?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&name=qq&level=1&page=0&size=20&sort=`


- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "name": "长江西路诱导牌",
                "level": 2,
                "address": "明珠广场",
                "novaCode": "54321",
                "maintainer": "zz"
            }
        ],
        "last": true,
        "totalElements": 1,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 1
    }
}
```

### 16.3.5 地图搜索查询诱导牌接口

- 功能描述:  根据name模糊查询所有相关诱导牌的信息
- 请求地址: `http://localhost:8080/guidance/screens/queryScreens`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/guidance/screens/queryScreens?access_token=4f5de152-f371-4b0c-a508-e3cd94d4783f&name=西`


- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 43,
            "coordinate": "117.313610 31.708892",
            "level": 1,
            "isOnline": false
        }
    ]
}
```

### 16.3.6 地图查询所有诱导牌位置接口

- 功能描述:  地图上查看所有诱导牌的地址
- 请求地址: `http://localhost:8080/guidance/screens/queryAddress`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/guidance/screens/queryAddress?access_token=4f5de152-f371-4b0c-a508-e3cd94d4783f`


- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 134,
            "name": "修改后的诱导牌",
            "coordinate": {
                "type": "Point",
                "coordinates": [
                    12,
                    67
                ]
            },
            "level": 2,
            "isOnline": false
        }
    ]
}
```

### 16.3.7 获取诱导牌的告警日志

- 功能描述:  获取诱牌的告警日志
- 请求地址: `http://domain/guidance/screens/{id}/failureLog`
- 请求动作: `GET`
- 请求示例: `http://domain/guidance/screens/43/failureLog?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 返回示例
{
    "case":"屏体电源断电",
    "date":"2017-12-28 12:00:00"
}

### 16.3.8 获取诱导牌下停车场

- 功能描述:  获取诱牌下的停车场
- 请求地址: `http://domain/guidance/screens/{id}/parkingArea`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/guidance/screens/75/parkingArea?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 返回示例
{
    "status": "SUCCESS",
    "data": {
        "id": 75,
        "name": "长江西路诱导牌",
        "address": "贵潜路口",
        "bizParkingAreaMapDtos": [
            {
                "name": "二级诱导屏天河河大厦",
                "remainNum": 1
            }
        ]
    }
}

## 16.4 led访问接口

### 16.4.1 新增led接口

- 功能描述:  新增led
- 请求地址: `http://domain:8080/guidance/leds`
- 请求动作: `POST`
- 请求示例: `http://domain:8080/guidance/leds?access_token=da9cd025-d3f6-4cc8-b472-1c9b94af0010`
- 请求示例
```
{
	"name":"led测试",
	"bizParkingAreasIds":[
	    49,44
	]
}
```
- 返回示例

```
{
    "status": "SUCCESS",
    "data": "Led屏幕信息保存成功"
}
```

### 16.4.2 根据id查询led信息接口

- 功能描述:  根据id查询led详情
- 请求地址: `http://domain:8080/guidance/leds/{id}`
- 请求动作: `GET`
- 请求示例: `http://domain/guidance/leds/100?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 100,
        "name": "修改后的LED",
        "index": null,
        "size": null,
        "ledBizParkingAreaDtos": [
            {
                "id": 93,
                "name": "二级诱导屏天河河大厦"
            }
        ],
        "screenName": null
    }
}
```


### 16.4.3 条件查询led接口

- 功能描述:  条件查询led信息
- 请求地址: `http://domain:8080/guidance/leds/search`
- 请求动作: `GET`
- 请求示例: `http://domain:8080/guidance/leds/search?access_token=da9cd025-d3f6-4cc8-b472-1c9b94af0010&page=0&size=1&name=led`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 90,
                "name": "led测试",
                "index": null,
                "size": null,
                "ledBizParkingAreaDtos": [],
                "screenName": null
            },
            {
                "id": 98,
                "name": "led测试12",
                "index": null,
                "size": null,
                "ledBizParkingAreaDtos": [],
                "screenName": null
            },
            {
                "id": 100,
                "name": "修改后的LED",
                "index": null,
                "size": null,
                "ledBizParkingAreaDtos": [
                    {
                        "id": 93,
                        "name": "二级诱导屏天河河大厦"
                    }
                ],
                "screenName": null
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 3,
        "number": 0,
        "size": 10,
        "sort": null,
        "first": true,
        "numberOfElements": 3
    }
}
```

### 16.4.4 查询未关联诱导牌的led接口

- 功能描述:  查询未关联诱导牌的led详情
- 请求地址: `http://domain:8080/guidance/leds/unrelated`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/guidance/leds/unrelated?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&screenId`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 90,
            "name": "led测试",
            "ledParkingAreaDtos": []
        }
    ]
}
```

### 16.4.5 编辑led信息

- 功能描述:  修改led信息
- 请求地址: `http://domain/guidance/leds/{id}`
- 请求动作: `PUT`
- 请求示例: `http://domain/guidance/leds/29?access_token=dd162dd1-26ec-45f4-a8ec-e99b00df4652`
- 请求示例
```
{
	"name":"修改led",
	"size":"64*32",
	"bizParkingAreaIds":[
	    44,49
	]
}
```

## 16.5 nova卡访问接口

### 16.5.1 新增nova接口

- 功能描述:  新增nova卡
- 请求地址: `http://domain:8080/guidance/novas`
- 请求动作: `POST`
- 请求示例: `http://domain:8080/guidance/novas?access_token=da9cd025-d3f6-4cc8-b472-1c9b94af0010`
- 请求示例
```
{
	"code":"Pluto2017baohesanji001",
	"simCode":"1111111111111"
}
```


### 16.5.2 根据id查询nova信息接口

- 功能描述:  根据id查询nova卡详情
- 请求地址: `http://domain:8080/guidance/novas/{id}`
- 请求动作: `GET`
- 请求示例: `http://domain:8080/guidance/novas/26?access_token=da9cd025-d3f6-4cc8-b472-1c9b94af0010`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 26,
        "code": "001",
        "sim": "1111111111111",
        "screen": null
    }
}
```
### 16.5.3 条件查询nova接口

- 功能描述:  条件查询nova卡详情
- 请求地址: `http://domain:8080/guidance/novas/search`
- 请求动作: `GET`
- 请求示例: `http://domain:8080/guidance/novas/search?access_token=da9cd025-d3f6-4cc8-b472-1c9b94af0010&page=0&size=1&code=1&sim=1`
- 返回示例

{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 54321,
                "code": "54321",
                "sim": "1213"
            },
            {
                "id": 103,
                "code": "Pluto2018001",
                "sim": "1111111111113"
            }
        ],
        "totalPages": 1,
        "totalElements": 2,
        "last": true,
        "number": 0,
        "size": 10,
        "sort": null,
        "first": true,
        "numberOfElements": 2
    }
}


### 16.5.4 查询未关联诱导牌的nova接口

- 功能描述: 查询未关联诱导牌的nova卡
- 请求地址: `http://domain:8080/guidance/novas/unrelated`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/guidance/novas/unrelated?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&screenId
- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 26,
            "code": "001",
            "sim": "1111111111111",
            "screen": null
        }
    ]
}
```

### 16.5.5 编辑nova卡信息

- 功能描述: 编辑nova卡的信息
- 请求地址: `http://domain:8080/guidance/novas/{id}`
- 请求动作: `PUT`
- 请求示例: `http://domian:8080/guidance/novas/26?access_token=dd162dd1-26ec-45f4-a8ec-e99b00df4652`
- 请求示例
```
{
	"code":"修改code",
	"simCode":"2222222222222"
}
```

### 16.5.6 下发重启nova卡指令

- 功能描述: 下发重启nova卡指令
- 请求地址: `http://domain:8080/guidance/novas/{code}/reboot`
- 请求动作: `POST`
- 请求示例: `http://domian:8080/guidance/novas/111111/reboot?access_token=dd162dd1-26ec-45f4-a8ec-e99b00df4652`
- 返回示例
```
{
    "status": "SUCCESS"
}
```

### 16.5.7 下发nova卡自检指令

- 功能描述: 下发nova卡自检指令
- 请求地址: `http://domain:8080/guidance/novas/{code}/checkSelf`
- 请求动作: `POST`
- 请求参数:
    - `code`: nova卡编号
- 请求示例: `http://domian:8080/guidance/novas/111111/checkSelf?access_token=dd162dd1-26ec-45f4-a8ec-e99b00df4652`
- 返回示例
```
{
    "status": "SUCCESS"
}
```

### 16.5.8 下发nova卡截屏指令

- 功能描述: 下发nova卡截屏指令
- 请求地址: `http://domain:8080/guidance/novas/{code}/screenCapture`
- 请求动作: `POST`
- 请求参数:
    - `code`: nova卡编号
- 请求示例: `http://domian:8080/guidance/novas/111111/screenCapture?access_token=dd162dd1-26ec-45f4-a8ec-e99b00df4652`
- 返回示例
```
{
    "status": "SUCCESS"
}
```

### 16.5.9 下发nova卡开关屏指令

- 功能描述: 下发nova卡开关屏指令
- 请求地址: `http://domain:8080/guidance/novas/{code}/screenControl?flag`
- 请求动作: `POST`
- 请求参数:
    - `code`: nova卡编号
    - `flag`: 开关屏标志，1开，2关
- 请求示例: `http://domian:8080/guidance/novas/111111/screenControl?access_token=dd162dd1-26ec-45f4-a8ec-e99b00df4652&flag=1`
- 返回示例
```
{
    "status": "SUCCESS"
}
```

### 16.5.10 查询nova卡状态

- 功能描述: 下发nova卡开关屏指令
- 请求地址: `http://domain:8080/guidance/novas/{code}/status`
- 请求动作: `GET`
- 请求参数:
    - `code`: nova卡编号
- 请求示例: `http://localhost:8092/novas/nova20170206001/status?access_token=1c39b4c7-629b-4b07-9e06-nova20170206001`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": "68b909d0-e622-46cf-8190-f67d22f1dc3a",
        "code": "nova20170206001",
        "isOnline": true
    }
}
```

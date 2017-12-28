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
    "coordinate":"117.313610 31.708892",
    "maintainer":"李冲",
    "maintainerPhoneNum":"18756578763",
    "parkingPositionQuantity":300,
    "source":1,  //数据来源，1：老系统上报，2是捷顺，3是摄像头上报
    "province":"",
    "city":"",
    "isOwnBusiness":false,
    "unitPrice":0,
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
    "coordinate":"117.313610 31.708892",
    "maintainer":"李冲",
    "maintainerPhoneNum":"18756578763",
    "parkingPositionQuantity":300,
    "source":1,  //数据来源，1：老系统上报，2是捷顺，3是摄像头上报
    "province":"",
    "city":"",
    "isOwnBusiness":false,
    "unitPrice":0,
}
```

- 返回示例
```
{
    "status": "SUCCESS",
    "data": "停车场信息更新成功"
}
```


### 16.1.3 获取商业停车场详情接口

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
        "coordinate": "117.313610 31.708892",
        "maintainer": "李冲",
        "maintainerPhoneNum": "18756578763",
        "parkingPositionQuantity":300,
        "source":1,  //数据来源，1：老系统上报，2是捷顺，3是摄像头上报
        "province":"",
        "city":"",
        "isOwnBusiness":false,
        "unitPrice":0,
        "leds": []
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
                "coordinate": "117.313610 31.708892",
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
                "coordinate": "117.313610 31.708892",
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
	"type":1,
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
	"bizParkingAreaId": 14
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
{
	"name":"长江西路诱导牌",
	"level":1,
	"novaId":1,
	"ledIds": [
		1,2,3,4
	],
	"district":"庐阳区",
	"address":"贵潜路口",
	"coordinate":"117.313610 31.708892",
	"maintainer": "zj"
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
	"coordinate":"117.313610 31.708892",
	"maintainer": "zz"
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
- 请求示例: `http://domain/guidance/screens/15?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`


- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "name": "长江西路诱导牌",
        "district": "庐阳区",
        "coordinate": "117.313610 31.708892",
        "address": "贵潜路口",
        "level": 1,
        "maintainer": "zj",
        "maintainerPhoneNum": null,
        "screenLedDtos": [
            {
                "name": "测试LED",
                "index": 1,
                "bizParkingAreas": []
            }
        ],
        "novaCode": "Pluto2017baohesanji001"
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
            "id": 43,
            "coordinate": "117.313610 31.708892",
            "level": 1,
            "isOnline": false
        },
        {
            "id": 53,
            "coordinate": "117.313610 31.708892",
            "level": 3,
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
	"bizParkingAreas":[]
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
- 请求示例: `http://domain:8080/guidance/leds/23?access_token=da9cd025-d3f6-4cc8-b472-1c9b94af0010`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 23,
        "name": "led",
        "index": null,
        "size": null,
        "novaCode": null,
        "bizParkingAreas": [],
        "screen": null
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
                "id": 23,
                "name": "led",
                "index": null,
                "size": null,
                "novaCode": null,
                "bizParkingAreas": [],
                "screen": null
            }
        ],
        "last": false,
        "totalPages": 6,
        "totalElements": 6,
        "number": 0,
        "size": 1,
        "sort": null,
        "first": true,
        "numberOfElements": 1
    }
}
```

### 16.4.4 查询未关联诱导牌的led接口

- 功能描述:  查询未关联诱导牌的led详情
- 请求地址: `http://domain:8080/guidance/leds/unrelated`
- 请求动作: `GET`
- 请求示例: `http://domain:8080/guidance/leds/unrelated?access_token=da9cd025-d3f6-4cc8-b472-1c9b94af0010`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 23,
            "name": "led",
            "index": null,
            "size": null,
            "novaCode": null,
            "bizParkingAreas": [],
            "screen": null
        },
        {
            "id": 1,
            "name": "led1",
            "index": 1,
            "size": null,
            "novaCode": null,
            "bizParkingAreas": [],
            "screen": null
        },
        {
            "id": 2,
            "name": "led2",
            "index": 2,
            "size": null,
            "novaCode": null,
            "bizParkingAreas": [],
            "screen": null
        },
        {
            "id": 3,
            "name": "led3",
            "index": 3,
            "size": null,
            "novaCode": null,
            "bizParkingAreas": [],
            "screen": null
        },
        {
            "id": 4,
            "name": "led4",
            "index": 4,
            "size": null,
            "novaCode": null,
            "bizParkingAreas": [],
            "screen": null
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
	"name":"修改led"
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
	"sim":"1111111111111"
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



### 16.5.4 查询未关联诱导牌的nova接口

- 功能描述: 查询未关联诱导牌的nova卡
- 请求地址: `http://domain:8080/guidance/novas/unrelated`
- 请求动作: `GET`
- 请求示例: `http://domain:8080/guidance/novas/unrelated?access_token=da9cd025-d3f6-4cc8-b472-1c9b94af0010`
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
	"sim":"2222222222222"
}
```

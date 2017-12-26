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
    "totalNum":300,
    "source":1
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
    "totalNum":300,
    "source":1
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
        "totalNum": 300,
        "source": 1,
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
                "totalNum": 300,
                "source": 1
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
                "totalNum": 300,
                "source": 1
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
        "leds": [
            {
                "id": 1,
                "name": "led1",
                "index": 1,
                "size": "96*48",
                "novaCode": null,
                "bizParkingAreas": [],
                "screen": null
            },
            {
                "id": 2,
                "name": "led2",
                "index": 2,
                "size": "96*48",
                "novaCode": null,
                "bizParkingAreas": [],
                "screen": null
            },
            {
                "id": 3,
                "name": "led3",
                "index": 3,
                "size": "96*48",
                "novaCode": null,
                "bizParkingAreas": [],
                "screen": null
            },
            {
                "id": 4,
                "name": "led4",
                "index": 4,
                "size": "96*48",
                "novaCode": null,
                "bizParkingAreas": [],
                "screen": null
            }
        ],
        "novaCode": "54321",
        "logs": [
            {
                "id": 1,
                "date": 1514165987000,
                "cause": "过热",
                "novaCode": "54321"
            },
            {
                "id": 2,
                "date": 1514079636000,
                "cause": "错点过多",
                "novaCode": "54321"
            }
        ]
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
## 10.1充电桩访问接口（ChargingStationController）
### 10.1.1 新建站点

- 功能描述:  新建站点
- 请求地址: `http://domain/pile/chargingStations`
- 请求动作: `POST`
- 请求示例: `http://domain/pile/chargingStations?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 请求数据示例  
```
{
	"code":"1",
	"name":"测试",
	 "coordinate": {
        "type": "Point",
        "coordinates": [
            12,
            67
        ]
    },
    "status":1, //站点状态:1.可用；2.停用
    "manufacturerName":"厂商",
    "manufacturerIco":null,
    "address":"",
    "dcNum":12,
    "acNum":10,
    "tags":[
    "24小时"
    ]
}
```

- 返回数据示例  
```$xslt
{
    "status": "SUCCESS"
}
```

### 10.1.2 查询站点信息

- 功能描述:  查询站点信息
- 请求地址: `http://domain/pile/chargingStations/{id}`
- 请求动作: `GET`
- 请求示例: `http://domain/pile/chargingStations/1?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例  
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "id": 8,
        "code": "1",
        "name": "测试",
        "coordinate": {
            "type": "Point",
            "coordinates": [
                12,
                67
            ]
        },
        "status": 1,
        "manufacturerName": "厂商",
        "manufacturerIco": null,
        "address": "",
        "dcNum": 12,
        "acNum": 10,
        "createdBy": "wyf",
        "createdDate": "2018-01-10",
        "lastModifiedDate": "2018-01-10",
        "lastModifiedBy": "wyf",
        "tags": [
            "24小时"
        ]
    }
}
```


### 10.1.3 通过站点编号更新站点信息

- 功能描述:  修改站点
- 请求地址: `http://domain/pile/chargingStations/{id}`
- 请求动作: `PUT`
- 请求示例: `http://domain/pile/chargingStations/1?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`


- 请求数据示例  
```
{
	"code":"1",
	"name":"测试",
	 "coordinate": {
        "type": "Point",
        "coordinates": [
            12,
            67
        ]
    },
    "status":1,
    "manufacturerName":"厂商",
    "manufacturerIco":null,
    "address":"",
    "dcNum":12,
    "acNum":10
}
```

- 返回数据示例  
```$xslt
{
    "status": "SUCCESS"
}
```

### 10.1.4 查询站点列表

- 功能描述:  查询站点列表
- 请求地址: `http://domain/pile/chargingStations`
- 请求动作: `GET`
- 请求示例: `http://domain/pile/chargingStations?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&name=&manufacturerName&status=`

- 返回数据示例  
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 8,
                "code": "1",
                "name": "测试1",
                "coordinate": {
                    "type": "Point",
                    "coordinates": [
                        12,
                        67
                    ]
                },
                "status": 1,
                "manufacturerName": "厂商",
                "manufacturerIco": null,
                "address": "",
                "dcNum": 12,
                "acNum": 10,
                "createdBy": "wyf",
                "createdDate": "2018-01-10",
                "lastModifiedDate": "2018-01-10",
                "lastModifiedBy": "wyf",
                "tags": null
            }
        ],
        "pageable": {
            "sort": {
                "sorted": false,
                "unsorted": true
            },
            "offset": 0,
            "pageSize": 20,
            "pageNumber": 0,
            "paged": true,
            "unpaged": false
        },
        "totalPages": 1,
        "totalElements": 1,
        "last": true,
        "size": 20,
        "number": 0,
        "numberOfElements": 1,
        "sort": {
            "sorted": false,
            "unsorted": true
        },
        "first": true
    }
}
```

### 10.1.5 上传厂商图标
- 功能描述:  上传厂商图标
- 请求地址: `http://domain/pile/chargingStations/uploadManufacturerIco`
- 请求动作: `POST`
- 请求示例: `http://domain/pile/chargingStations/uploadManufacturerIco?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
  ![Markdown](http://i1.buimg.com/1949/84c15df0a215c259.png)

- 返回数据示例 
```$xslt
{
  "status": "SUCCESS",
  "data": "7c0b9fb4-fedc-483f-b7ab-3fd5d5e07327.jpg"
}
```

### 10.1.6 删除厂商图标

- 功能描述:  删除厂商图标
- 请求地址: `http://domain/pile/chargingStations/deleteManufacturerIco`
- 请求动作: `DELETE`
- 请求示例: `http://domain/pile/chargingStations/deleteManufacturerIco?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&name=
  ![Markdown](http://i1.buimg.com/1949/84c15df0a215c259.png)
  
- 返回数据示例 
```$xslt
{
    "status": "SUCCESS",
    "data": "7c0b9fb4-fedc-483f-b7ab-3fd5d5e07327.jpg"
}
```

### 10.1.7 获取厂商图标
- 功能描述:  根据图片名称获取厂商图标
- 请求地址: `http://domain/pile/chargingStations/getManufacturerIco`
- 请求动作: `GET`
- 请求示例: `http://domain/pile/chargingStations/getManufacturerIco?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&name=

- 返回数据示例  
![Markdown](http://i2.kiimg.com/1949/7c84a20ddd1f1eaa.png)

### 10.1.8 导出站点列表
- 功能描述:  导出站点列表
- 请求地址: `http://domain/pile/chargingStations/export`
- 请求动作: `GET`
- 请求示例: `http://domain/pile/chargingStations/export?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&name=&manufacturerName&status=`

### 10.1.9 获取所有站点列表
- 功能描述:  获取所有站点列表
- 请求地址: `http://domain/pile/chargingStations/findAll`
- 请求动作: `GET`
- 请求示例: `http://domain/pile/chargingStations/findAll?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例 
    - `status`:站点状态:1.可用；2.停用
```$xslt
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 8,
            "code": "1",
            "name": "测试1",
            "coordinate": {
                "type": "Point",
                "coordinates": [
                    12,
                    67
                ]
            },
            "status": 1,
            "manufacturerName": "厂商",
            "manufacturerIco": null,
            "address": "",
            "dcNum": 12,
            "acNum": 10,
            "createdBy": "wyf",
            "createdDate": "2018-01-10",
            "lastModifiedDate": "2018-01-10",
            "lastModifiedBy": "wyf",
            "tags": [
                "24小时"
            ]
        }
    ]
}
```

### 10.1.10 判断充电桩编码是否已存在
- 功能描述:  判断充电桩编码是否已存在
- 请求地址: `http://domain/pile/chargingStations/findCodeExist?access_token=f2ca8520-11a9-415b-9d15-21690acbb369&code=12`
- 请求动作: `GET`
- 请求示例: `http://domain/pile/chargingStations/findCodeExist?access_token=f2ca8520-11a9-415b-9d15-21690acbb369&code=12`


- 返回数据示例 
    - `data`:true:已使用；false:未使用

```$xslt  
{
    "status": "SUCCESS",
    "data": false
}
```
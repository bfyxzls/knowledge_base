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
    "acNum":10
}
```

- 返回数据示例  
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "id": 6,
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
        "createdDate": 1510569381322,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1510569381322
    }
}
```

#### 10.1.2 查询站点信息

- 功能描述:  查询站点信息
- 请求地址: `http://domain/pile/chargingStations/{id}`
- 请求动作: `GET`
- 请求示例: `http://domain/pile/chargingStations/1?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例  
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "id": 6,
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
        "createdDate": 1510569381322,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1510569381322
    }
}
```


#### 10.1.3 通过站点编号更新站点信息

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
    "status": "SUCCESS",
    "data": {
        "id": 6,
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
        "createdDate": 1510569381322,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1510569381322
    }
}
```

#### 10.1.4 查询站点列表

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
                "id": 2,
                "code": "123",
                "name": "123",
                "coordinate": null,
                "status": 2,
                "manufacturerName": "123",
                "manufacturerIco": "123",
                "address": "123",
                "dcNum": 12,
                "acNum": 12,
                "createdBy": "wyf",
                "createdDate": 1510197969918,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1510197969918
            },
            {
                "id": 1,
                "code": "123",
                "name": "123",
                "coordinate": null,
                "status": 2,
                "manufacturerName": "123",
                "manufacturerIco": "123",
                "address": "123",
                "dcNum": 12,
                "acNum": 12,
                "createdBy": "wyf",
                "createdDate": 1510197946664,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1510198286042
            },
            {
                "id": 6,
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
                "createdDate": 1510569381322,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1510569381322
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 3,
        "size": 10,
        "number": 0,
        "first": true,
        "sort": null,
        "numberOfElements": 3
    }
}
```

#### 10.1.5 上传厂商图标
- 功能描述:  上传厂商图标
- 请求地址: `http://domain/pile/uploadManufacturerIco`
- 请求动作: `POST`
- 请求示例: `http://domain/pile/uploadManufacturerIco?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
  ![Markdown](http://i1.buimg.com/1949/84c15df0a215c259.png)

- 返回数据示例 
```$xslt
{
  "status": "SUCCESS",
  "data": "7c0b9fb4-fedc-483f-b7ab-3fd5d5e07327.jpg"
}
```

#### 10.1.6 删除厂商图标

- 功能描述:  删除厂商图标
- 请求地址: `http://domain/pile/deleteManufacturerIco`
- 请求动作: `DELETE`
- 请求示例: `http://domain/pile/deleteManufacturerIco?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&name=
  ![Markdown](http://i1.buimg.com/1949/84c15df0a215c259.png)
  
- 返回数据示例 
```$xslt
{
    "status": "SUCCESS",
    "data": "7c0b9fb4-fedc-483f-b7ab-3fd5d5e07327.jpg"
}
```

#### 10.1.7 获取厂商图标
- 功能描述:  根据图片名称获取厂商图标
- 请求地址: `http://domain/pile/getManufacturerIco`
- 请求动作: `GET`
- 请求示例: `http://domain/pile/getManufacturerIco?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&name=

- 返回数据示例  
![Markdown](http://i2.kiimg.com/1949/7c84a20ddd1f1eaa.png)

#### 10.1.8 导出站点列表
- 功能描述:  导出站点列表
- 请求地址: `http://domain/pile/chargingStations/export`
- 请求动作: `GET`
- 请求示例: `http://domain/pile/chargingStations/export?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&name=&manufacturerName&status=`

#### 10.1.9 获取所有站点列表
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
            "id": 2,
            "code": "123",
            "name": "123",
            "coordinate": null,
            "status": 2,
            "manufacturerName": "123",
            "manufacturerIco": "123",
            "address": "123",
            "dcNum": 12,
            "acNum": 12
        },
        {
            "id": 1,
            "code": "123",
            "name": "123",
            "coordinate": null,
            "status": 2,
            "manufacturerName": "123",
            "manufacturerIco": "123",
            "address": "123",
            "dcNum": 12,
            "acNum": 12
        },
        {
            "id": 6,
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
            "acNum": 10
        }
    ]
}
```
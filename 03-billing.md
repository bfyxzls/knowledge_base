## 3.1 收费策略（ChargingStrategy）
### 3.1.1 save接口
- 功能描述: 新增一个收费策略，并保存进数据库
- 请求地址: `http://domain/billing/chargingStrategies?access_token=token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/billing/chargingStrategies?access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea`
-Body:
```
{
    "name": "肥西C级全日收费策略",
    "description": null,
    "chargingType": "time"
}
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1008,
        "name": "肥西C级全日收费策略",
        "freePeriod": null,
        "chargingType": "time",
        "freePeriodChargeable": null,
        "description": null,
        "chargingStandards": null
    }
}
```
### 3.1.2 getFee接口
- 功能描述: 计算驶出车辆此次的停车费用
- 请求地址: 
```
http://domain/billing/chargingStrategies/fee?access_token=token&
chargingStrategyId=_chargingStrategyId&
startTime=_startTime&
vehicleType=_vehicleType
```
- 请求动作: `GET`
- 请求示例: 
```
http://localhost:8080/billing/chargingStrategies/fee?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431
&chargingStrategyId=1000&startTime=2017-12-14 8:00:00&vehicleType=04
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "fee": 11,
        "calculatedFee": 11
        "endTime": "2017-07-19 09:43:25"
        "parkingPeriod": 134
    }
}
```
### 3.1.3 list接口
- 功能描述: 查找收费策略列表
- 请求地址: `http://domain/billing/chargingStrategies?access_token=token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/billing/chargingStrategies?access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "name": "肥西A级全日收费策略",
                "id": 1000,
                "description": null,
                "chargingType": "time"
            },
            {
                "name": "肥西A级全日收费策略\n",
                "id": 1001,
                "description": null,
                "chargingType": "once"
            },
            {
                "name": "肥西B级全日收费策略",
                "id": 1002,
                "description": null,
                "chargingType": "time"
            },
            {
                "name": "肥西B级全日收费策略",
                "id": 1003,
                "description": null,
                "chargingType": "once"
            },
            {
                "name": "AA",
                "id": 1007,
                "description": null,
                "chargingType": null
            }
        ],
        "last": true,
        "totalElements": 5,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 5
    }
}
```
### 3.1.4 get接口
- 功能描述: 根据Id查找收费策略
- 请求地址: `http://domain/billing/chargingStrategies/{id}?access_token=token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/billing/chargingStrategies/1000?access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1000,
        "name": "肥西A级全日收费策略",
        "freePeriod": 15,
        "chargingType": "time",
        "freePeriodChargeable": true,
        "description": null,
        "chargingStandards": [
            {
                "chargingStartTime": "07:30:00",
                "chargingEndTime": "19:00:00",
                "maxFee": 5000,
                "chargingRules": [
                    {
                        "id": 1000,
                        "interval": 30,
                        "unit": 30,
                        "unitCost": 300,
                        "sort": 1
                    },
                    {
                        "id": 1001,
                        "interval": 60,
                        "unit": 30,
                        "unitCost": 200,
                        "sort": 2
                    },
                    {
                        "id": 1002,
                        "interval": 0,
                        "unit": 30,
                        "unitCost": 100,
                        "sort": 3
                    }
                ],
                "id": 1000,
                "dateType": 1,
                "vehicleType": 1
            },
            {
                "chargingStartTime": "07:30:00",
                "chargingEndTime": "19:00:00",
                "maxFee": 5000,
                "chargingRules": [
                    {
                        "id": 1003,
                        "interval": 60,
                        "unit": 30,
                        "unitCost": 400,
                        "sort": 1
                    },
                    {
                        "id": 1004,
                        "interval": 60,
                        "unit": 30,
                        "unitCost": 300,
                        "sort": 2
                    },
                    {
                        "id": 1005,
                        "interval": 0,
                        "unit": 30,
                        "unitCost": 200,
                        "sort": 3
                    }
                ],
                "id": 1001,
                "dateType": 1,
                "vehicleType": 2
            },
            {
                "chargingStartTime": "07:30:00",
                "chargingEndTime": "19:00:00",
                "maxFee": 5000,
                "chargingRules": [
                    {
                        "id": 1006,
                        "interval": 60,
                        "unit": 30,
                        "unitCost": 400,
                        "sort": 1
                    },
                    {
                        "id": 1007,
                        "interval": 0,
                        "unit": 30,
                        "unitCost": 300,
                        "sort": 2
                    }
                ],
                "id": 1002,
                "dateType": 2,
                "vehicleType": 1
            },
            {
                "chargingStartTime": "07:30:00",
                "chargingEndTime": "19:00:00",
                "maxFee": 5000,
                "chargingRules": [
                    {
                        "id": 1008,
                        "interval": 60,
                        "unit": 30,
                        "unitCost": 500,
                        "sort": 1
                    },
                    {
                        "id": 1009,
                        "interval": 0,
                        "unit": 30,
                        "unitCost": 400,
                        "sort": 2
                    }
                ],
                "id": 1003,
                "dateType": 2,
                "vehicleType": 2
            }
        ]
    }
}
```
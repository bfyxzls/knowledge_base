# 6.1 Customer Controller接口

### 6.1.1 更新用户接口

- 功能描述:  修改用户基本信息
- 请求地址: `http://domain/customer/customers/{id}`
- 请求动作: `PUT`
- 请求示例: `http://domain/customer/customers/1004?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 请求数据示例  
```
{
	"realName":"张三",
	"gender":1,
    "email":"1221434@qq.com",
    "nickname":"zz"
}
```

### 6.1.2 查询用户信息接口

- 功能描述:  查询用户基本信息
- 请求地址: `http://domain/customer/customers/myInfo`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/customers/myInfo?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1004,
        "realName": "张三",
        "nickname": "zz",
        "phoneNum": "12345678910",
        "email": "1221434@qq.com",
        "gender": 1,
        "vehicles": []
    }
}
```


### 6.1.3 上传用户头像接口

- 功能描述:  上传用户头像
- 请求地址: `http://domain/zuul/customer/customers/uploadAvator`
- 请求动作: `PUT`
- 请求示例: `http://domain/zuul/customer/customers/uploadAvator?id=1004&access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
  ![Markdown](http://i1.buimg.com/1949/84c15df0a215c259.png)

- 请求数据示例  
```
{
    "status": "SUCCESS"
}
```

### 6.1.4 获取用户头像接口

- 功能描述:  获取用户头像
- 请求地址: `http://domain/customer/customers/{id}/avator`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/customers/1004/avator?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例  

    ![Markdown](http://i2.kiimg.com/1949/7c84a20ddd1f1eaa.png)

    ​

### 6.1.5 绑定车辆接口

- 功能描述:  绑定车辆
- 请求地址: `http://domain/customer/customers/vehicleBinding`
- 请求动作: `PUT`
- 请求示例: `http://domain/customer/customers/vehicleBinding?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 请求数据示例  
```
{
   "customerId":1004,
   "vehicleType":"02",
   "carPlate":"皖A12345"，
   "vin":"123456"
}
```

### 6.1.6 解绑车辆接口

- 功能描述:  解绑车辆
- 请求地址: `http://domain/customer/customers/vehicleUnbinding`
- 请求动作: `PUT`
- 请求示例: `http://domain/customer/customers/vehicleUnbinding?customerId=1004&vehicleId=1001&access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 请求数据示例  
```
{
    "status":true,
    "data":"车辆解绑成功"
}
```
### 6.1.7 getVehicleFeeStats接口
- 功能描述:  获取当前客户的待支付和待补缴的订单
- 请求地址: `http://localhost:8080/customer/customers/getVehicleFeeStats`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/customer/customers/getVehicleFeeStats?access_token`

- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "carPlate": "皖AYN056",
            "numOfArrears": 0,
            "numOfCurrentFee": 0
        }
    ]
}
```
## 6.2 月票（MonthBill）
PS:需要用admin用户获得access_token
### 6.2.1 get接口
- 功能描述: 根据id查找该MonthBill的详细信息
- 请求地址: `http://domain/customer/monthBills/{id}?access_token=token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/customer/monthBills/1000?access_token=8f3a8e76-fd86-49c6-9bf2-5f42563c2486`

- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1000,
        "customerCarPlate": "皖A12346",
        "customerName": "高颖",
        "customerPhoneNum": "133333333333",
        "customerCardNum": "325452155845245865",
        "startMonth": "2017-08-01 08:00:00",
        "endMonth": "2017-10-31 08:00:00",
        "roadSectionIds": [
            1036
        ],
        "shouldPay": 10000,
        "actualPay": 10000,
        "valid": true,
        "description": null
    }
}
```
### 6.2.2 list接口
- 功能描述: 查找MonthBill列表
- 请求地址: `http://domain/customer/monthBills?access_token=token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/customer/monthBills?access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea`

- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1000,
                "customerCarPlate": "皖A12346",
                "customerName": "高颖",
                "customerPhoneNum": "133333333333",
                "customerCardNum": "325452155845245865",
                "startMonth": "2017-08-01 08:00:00",
                "endMonth": "2017-10-31 08:00:00",
                "roadSectionIds": [
                    1036
                ],
                "shouldPay": 10000,
                "actualPay": 10000,
                "valid": true,
                "description": null
            },
            {
                "id": 1001,
                "customerCarPlate": "皖A54321",
                "customerName": "孟阿瑾",
                "customerPhoneNum": "133333333335",
                "customerCardNum": "325452155845245262",
                "startMonth": "2017-08-01 08:00:00",
                "endMonth": "2017-10-31 08:00:00",
                "roadSectionIds": [
                    1020
                ],
                "shouldPay": 10000,
                "actualPay": 10000,
                "valid": true,
                "description": null
            }
        ],
        "last": true,
        "totalElements": 2,
        "totalPages": 1,
        "size": 20,
        "number": 0,
        "sort": null,
        "first": true,
        "numberOfElements": 2
    }
}
```
### 6.2.3 save接口
- 功能描述: 新增一个MonthBill，并保存进数据库
- 请求地址: `http://domain/customer/monthBills?access_token=token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/customer/monthBills/?access_token=8f3a8e76-fd86-49c6-9bf2-5f42563c2486`
- Body：
```
{
    "customerCarPlate": "皖A12346",
    "customerName": "高颖",
    "customerPhoneNum": "133333333333",
    "customerCardNum": "325452155845245865",
    "startMonth": 1501545600000,
    "endMonth": 1509408000000,
    "roadSectionIds": [
        1036
    ],
    "shouldPay": 10000,
    "actualPay": 10000,
    "valid": true,
    "description": null
}
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1000,
        "customerCarPlate": "皖A12346",
        "customerName": "高颖",
        "customerPhoneNum": "133333333333",
        "customerCardNum": "325452155845245865",
        "startMonth": 1501545600000,
        "endMonth": 1509408000000,
        "roadSectionIds": [
            1036
        ],
        "shouldPay": 10000,
        "actualPay": 10000,
        "valid": true,
        "description": null
    }
}
```
### 6.2.4 update接口
- 功能描述: 传入Id，更新该MonthBill
- 请求地址: `http://domain/customer/monthBills/{id}?access_token=token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/customer/monthBills/1000?access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea`
- Body：
```
{
    "customerName": "ygao"
}
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1000,
        "customerCarPlate": "皖A12346",
        "customerName": "ygao",
        "customerPhoneNum": "133333333333",
        "customerCardNum": "325452155845245865",
        "startMonth": "2017-08-01 08:00:00",
        "endMonth": "2017-10-31 08:00:00",
        "roadSectionIds": [
            1036
        ],
        "shouldPay": 10000,
        "actualPay": 10000,
        "valid": true,
        "description": null
    }
}
```
### 6.2.5 check接口
- 功能描述: 传入车牌号和路段Id，查看该车在该路段是否具有月票
- 请求地址: `http://domain/customer/monthBills/checkMonthBill?access_token=token&customerCarPlate=_customerCarPlate&roadSectionId=_roadSectionId`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/customer/monthBills/checkMonthBill?access_token=8f3a8e76-fd86-49c6-9bf2-5f42563c2486&customerCarPlate=皖A54321&roadSectionId=1020`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": true
}
```

## 6.3 统计（Stats）

### 6.3.1 统计最近一周用户注册量

- 功能描述: 统计最近一周用户注册量
- 请求地址: `localhost:8080/customer/stats/todayRegisterNumByWeek?access_token=4d04bb9b-6941-4db0-a52f-a74e4f3b8219`
- 请求动作: `GET`
- 请求示例: `localhost:8080/customer/stats/todayRegisterNumByWeek?access_token=4d04bb9b-6941-4db0-a52f-a74e4f3b8219`
- 返回示例

```json
{
    "status": "SUCCESS",
    "data": {
        "totalNum": 3,
        "registerNumStatsGroupByDays": [
            {
                "day": "2017-08-25",
                "num": 1
            },
            {
                "day": "2017-08-28",
                "num": 1
            },
            {
                "day": "2017-08-29",
                "num": 1
            }
        ]
    }
}
```


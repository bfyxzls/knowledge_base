## 6.1 Customer Controller接口

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
- 返回数据示例  
```$xslt
{
    "status": "SUCCESS",
    "data": "更新客户成功"
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
        "id": 1001,
        "realName": "张三",
        "nickname": "zz",
        "phoneNum": "15555417041",
        "email": "1221434@qq.com",
        "gender": 1,
        "vehicles": [
            {
                "id": 1035,
                "carPlate": "皖A12345",
                "vehicleType": "02",
                "vin": "999999"
            },
            {
                "id": 1053,
                "carPlate": "赣HHHUHH",
                "vehicleType": "02",
                "vin": "586869"
            },
            {
                "id": 1054,
                "carPlate": "闽YYJVVU",
                "vehicleType": "02",
                "vin": "786686"
            },
            {
                "id": 1055,
                "carPlate": "青GGHUHJ",
                "vehicleType": "02",
                "vin": "568869"
            },
            {
                "id": 1057,
                "carPlate": "辽RYYYYU",
                "vehicleType": "02",
                "vin": "258585"
            },
            {
                "id": 1058,
                "carPlate": "闽HHKHGH",
                "vehicleType": "02",
                "vin": "883868"
            },
            {
                "id": 1059,
                "carPlate": "皖A58881",
                "vehicleType": "02",
                "vin": "888858"
            },
            {
                "id": 1061,
                "carPlate": "皖A58883",
                "vehicleType": "02",
                "vin": "888888"
            }
        ],
        "createdTime": 1503945908000
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
- 返回数据示例 
```$xslt
{
    "status": "SUCCESS",
    "data": "车辆绑定成功"
}
```

### 6.1.6 解绑车辆接口

- 功能描述:  解绑车辆
- 请求地址: `http://domain/customer/customers/vehicleUnbinding`
- 请求动作: `PUT`
- 请求示例: `http://domain/customer/customers/vehicleUnbinding?customerId=1004&vehicleId=1001&access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例  
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
            "carPlate": "皖A12345",
            "numOfArrears": 0,
            "numOfOnParking": 34,
            "parkingOrderIdsToBePaid": [
                10000458,
                10000457,
                10000330,
                10000399,
                10000400,
                10000401,
                10000403,
                10000404,
                10000405,
                10000406,
                10000407,
                10000421,
                10000428,
                10000429,
                10000430,
                10000431,
                10000434,
                10000424,
                10000432,
                10000433,
                10000435,
                10000282,
                10000277,
                10000286,
                10000306,
                10000298,
                10000299,
                10000284,
                10000423,
                10000426,
                10000419,
                10000422,
                10000427,
                10000425
            ]
        },
        {
            "carPlate": "赣HHHUHH",
            "numOfArrears": 0,
            "numOfOnParking": 0,
            "parkingOrderIdsToBePaid": []
        },
        {
            "carPlate": "闽YYJVVU",
            "numOfArrears": 0,
            "numOfOnParking": 0,
            "parkingOrderIdsToBePaid": []
        },
        {
            "carPlate": "青GGHUHJ",
            "numOfArrears": 0,
            "numOfOnParking": 0,
            "parkingOrderIdsToBePaid": []
        },
        {
            "carPlate": "辽RYYYYU",
            "numOfArrears": 0,
            "numOfOnParking": 0,
            "parkingOrderIdsToBePaid": []
        },
        {
            "carPlate": "闽HHKHGH",
            "numOfArrears": 0,
            "numOfOnParking": 0,
            "parkingOrderIdsToBePaid": []
        },
        {
            "carPlate": "皖A58881",
            "numOfArrears": 1,
            "numOfOnParking": 0,
            "parkingOrderIdsToBePaid": []
        },
        {
            "carPlate": "皖A58883",
            "numOfArrears": 1,
            "numOfOnParking": 2,
            "parkingOrderIdsToBePaid": [
                10000347,
                10000397
            ]
        }
    ]
}
```
### 6.1.8 查询用户信息接口

- 功能描述:  查询用户车辆信息
- 请求地址: `http://domain/customer/customers/obtainVehicles`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/customers/obtainVehicles?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1034,
            "carPlate": "皖AYN056",
            "vehicleType": "02",
            "vin": "191433"
        }
    ]
}
```

### 6.1.9 车辆超时未驶离推送提醒

- 功能描述: 车辆超时未驶离推送提醒
- 请求地址: `http://domain/customer/customers/vehicleNotLeaveNotify`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/customer/customers/vehicleNotLeaveNotify?carPlate=京A12346&access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 返回数据示例 

```json
{
    "status": "SUCCESS"
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

### 6.2.6 query接口
- 功能描述: 根据车牌，用户姓名，或者手机号码查询月票信息
- 请求地址: `http://domain/customer/monthBills/query?access_token`
         或 `http://domain/customer/monthBills/query?access_token&customerCarPlate`
         或 `http://domain/customer/monthBills/query?access_token&customerCarPlate&customerName`
         或 `http://domain/customer/monthBills/query?access_token&customerCarPlate&customerName&customerPhoneNum`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/monthBills/query?access_token=662b6404-298e-4194-812e-3d64bc551173&customerCarPlate=皖A95276&customerName=张三&customerPhoneNum=18622031202&page=0&size=10&sort=id,ASC`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1000,
                "customerCarPlate": "皖A95276",
                "customerName": "张三",
                "customerPhoneNum": "18622031202",
                "customerCardNum": "342501199111231023",
                "startMonth": "2017-09-01 00:00:00",
                "endMonth": "2017-12-31 23:59:59",
                "roadSectionIds": [
                    1000
                ],
                "shouldPay": 1000,
                "actualPay": 100,
                "valid": true,
                "description": "赊账900",
                "createdBy": "wyf",
                "createdDate": 1504804324159,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504804324159
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 1,
        "sort": [
            {
                "direction": "ASC",
                "property": "id",
                "ignoreCase": false,
                "nullHandling": "NATIVE",
                "ascending": true,
                "descending": false
            }
        ],
        "first": true,
        "numberOfElements": 1,
        "size": 10,
        "number": 0
    }
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

## 6.4 电子发票抬头

### 6.4.1 新增电子发票抬头接口

- 功能描述: 增加电子发票抬头

- 请求地址: `localhost:8080/customer/titles`

- 请求动作: `POST`

- 请求示例: `localhost:8080/customer/titles?access_token=1e2bebe0-1f79-4d84-a2cd-86f6be3f7359`

- 请求示例

```
{
		"title":"个人",
		"buyerId":"123",
		"isDefault":false,
		"phoneNum":"15555417041"
	}
```

### 6.4.2 list接口

- 功能描述: 电子发票抬头list

- 请求地址: `localhost:8080/customer/titles`

- 请求动作: `GET`

- 请求示例: `localhost:8080/customer/titles?access_token=1e2bebe0-1f79-4d84-a2cd-86f6be3f7359&PhoneNum=15555417041`

- 请求示例

```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 16,
            "title": "个人",
            "buyerId": "123",
            "isDefault": false,
            "phoneNum": "15555417041"
        },
        {
            "id": 22,
            "title": "公司",
            "buyerId": "456",
            "isDefault": true,
            "phoneNum": "15555417041"
        }
    ]
}
```

### 6.4.3 修改发票抬头信息接口
   
  - 功能描述: 修改发票抬头信息
   
  - 请求地址: `http://localhost:8080/customer/titles/`
   
  - 请求动作: `PUT`
   
  - 请求示例: `http://localhost:8080/customer/titles/16?access_token=1e2bebe0-1f79-4d84-a2cd-86f6be3f7359`
   
  - 请求示例
   
   ```
   {
   		"title":"个人修改",
   		"buyerId":"777",
   		"isDefault":true,
   		"phoneNum":"15555417041"
   	}
   ```
  - 返回示例
   
   ```
   {
       "status": "SUCCESS",
       "data": "更新发票抬头成功"
   }
   ```

### 6.4.4 获取默认发票抬头接口

- 功能描述: 设置发票为默认抬头

- 请求地址: `http://localhost:8080/customer/titles/default`

- 请求动作: `PUT`

- 请求示例: `http://localhost:8080/customer/titles/defaultTitle?access_token=1e2bebe0-1f79-4d84-a2cd-86f6be3f7359&PhoneNum=15555417041`

- 返回示例

```
 {
   		"title":"个人修改",
   		"buyerId":"777",
   		"isDefault":true,
   		"phoneNum":"15555417041"
   	}
  ```

### 6.4.5 查询发票抬头信息接口

- 功能描述: 查询发票抬头信息

- 请求地址: `http://localhost:8080/customer/titles`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/customer/titles/16?access_token=1e2bebe0-1f79-4d84-a2cd-86f6be3f7359`

- 返回示例

```
{
    "status": "SUCCESS",
    "data": {
        "id": 16,
        "title": "个人修改",
        "buyerId": "777",
        "isDefault": false,
        "phoneNum": "15555417041"
    }
}
```
### 6.4.6 删除发票抬头信息

- 功能描述: 删除发票抬头

- 请求地址: `localhost:8080/customer/titles`

- 请求动作: `DELETE`

- 请求示例: `http://localhost:8080/customer/titles/5?access_token=1e2bebe0-1f79-4d84-a2cd-86f6be3f7359`

- 返回示例

```
{
    "status": "SUCCESS",
    "data": "发票抬头删除成功"
}
```

## 6.5  发票订单（InvoiceOrder）
### 6.5.1 查询指定区域下的发票订单信息
- 功能描述: 查询指定区域下的发票订单信息

- 请求地址: `localhost:8080/customer/invoiceOrders/obtainInvoiceOrdersInGivenDistrict?access_token&districtId`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/customer/invoiceOrders/obtainInvoiceOrdersInGivenDistrict?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&districtId=1002`

- 返回示例
```aidl
{
    "status": "SUCCESS",
    "data": [
        {
            "completeDate": "2017-09-14 15:13:14 星期四",
            "isMonthBill": false,
            "roadSectionName": "潜山路-长江西路",
            "parkingPeriod": 287,
            "fee": 0
        },
        {
                    "completeDate": "2017-12-08 22:13:14 星期五",
                    "isMonthBill": false,
                    "roadSectionName": "潜山路-长江西路",
                    "parkingPeriod": 2252,
                    "fee": 4000
                }
            ]
        }
```
### 6.5.1 查询指定电子订单下的发票订单信息
- 功能描述: 查询指定电子订单下的发票订单信息

- 请求地址: `localhost:8080/customer/invoiceOrders/obtainInvoiceOrdersInGivenInvoice?access_token&invoiceId`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/customer/invoiceOrders/obtainInvoiceOrdersInGivenInvoice?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&invoiceId=78`

- 返回示例
```aidl
{
    "status": "SUCCESS",
    "data": [
        {
            "completeDate": "2017-09-14 15:13:14 星期四",
            "isMonthBill": false,
            "roadSectionName": "潜山路-长江西路",
            "parkingPeriod": 286,
            "fee": 4000
        },
        {
            "completeDate": "2017-09-15 15:13:14 星期五",
            "isMonthBill": false,
            "roadSectionName": "潜山路-长江西路",
            "parkingPeriod": 301,
            "fee": 4000
        },
        {
            "completeDate": "2017-09-15 19:00:00 星期五",
            "isMonthBill": false,
            "roadSectionName": "潜山路-长江西路",
            "parkingPeriod": 218,
            "fee": 1000
        }
    ]
}

```




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
### 6.1.8 查询用户车辆信息接口

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
- 请求示例: `http://localhost:8080/customer/monthBills/?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`
- Body：
```
{
    "customerCarPlate": "皖A12346",
    "customerName": "梁伟",
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
    "description": null,
    "district":1
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
### 6.2.7 根据发票信息查询月票信息详情

- 功能描述: 根据月票发票查询月票详情
- 请求地址: `http://domain:8080/customer/web/invoices/{id}/monthBill`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/customer/web/invoices/170/monthBill?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`
- 返回示例

```
{
    "status": "SUCCESS",
    "data": [
        {
            "customerCarPlate": "皖A12346",
            "customerPhoneNum": "133333333333",
            "roadSections": [
                {
                    "name": "望江西路",
                    "id": 1001,
                    "parkingAreaName": "888"
                },
                {
                    "name": "长江西路",
                    "id": 1002,
                    "parkingAreaName": "植保路"
                }
            ],
            "endMonth": 1527696000000,
            "createDate": 1513216430374,
            "actualPay": 10000
        }
    ]
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
## 6.4 支付接口

### 6.4.1支付宝生成App支付订单信息接口

- 功能描述：支付宝生成订单信息接口
- 请求地址：`http://doman/customer/alipay/generateAppMonthBillInfo`
- 请求动作：`POST`
- 请求示例：`http://hocalhost:8080/customer/alipay/generateAppMonthBillInfo?access_token=d0f17df9-1bc5-4fde-b7d1-6ee9f5605cc3`
```json
 {
     "customerCarPlate": "皖A12346",
     "customerName": "梁伟",
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
     "description": null,
     "district":1
 }
```
- 返回示例：

```
{
    "status": "SUCCESS",
    "data": "alipay_sdk=alipay-sdk-java-dynamicVersionNo&app_id=2017082908447174&biz_content=%7B%22body%22%3A%22%E6%9C%88%E7%A5%A8%E7%BC%B4%E8%B4%B9%22%2C%22out_trade_no%22%3A%22201712151921366189130%22%2C%22product_code%22%3A%22QUICK_MSECURITY_PAY%22%2C%22subject%22%3A%22%E6%9C%88%E7%A5%A8%E7%BC%B4%E8%B4%B9%22%2C%22timeout_express%22%3A%2230m%22%2C%22total_amount%22%3A%22100.0%22%7D&charset=UTF-8&format=json&method=alipay.trade.app.pay&notify_url=http%3A%2F%2Fhfcb.asuscomm.com%3A9080%2Fcustomer%2Falipay%2Fcallback%2FappMonthBillPaymentNotify&sign=GzpKXG5A8Om85vqb8Q2U6fPHrUEUFiOtv7zHj%2FIrASftJROJdX54rnf32rCqKTSCwQOsMpqRxyY5eAb35KpS%2BIwKo9i4rOOnjT2%2FuzDl8FV1greGrYbfyRf0B3TB7UyXU7udJIQ1PEczjjpBBl5WlCzEYbupvv6Q6fyUtC%2FB6dUIivxbg7yCSN6b5YmazOr%2BE%2BHrqbjdhAQkLn0JV%2FjjZ26TU%2BHFqTqZKNr20xgPN4mHzyeNGqLTKBAyZ%2B9DnXANvMXDZKljUvxjj4ieo2ZsP6dIq4xUs5VdtS5j9qgfid5z5YkK7JAttsmOEACn1LWAespzr2Hxf4nPdRxvSuZPuA%3D%3D&sign_type=RSA2&timestamp=2017-12-15+19%3A21%3A36&version=1.0"
}
```


### 6.4.2 微信生成App支付订单信息接口

- 功能描述：微信生成订单信息接口
- 请求地址：`http://doman/customer/weChat/generateAppMonthBillInfo`
- 请求动作：`POST`
- 请求示例：`http://localhost:8080/customer/weChat/generateAppMonthBillInfo?access_token=d0f17df9-1bc5-4fde-b7d1-6ee9f5605cc3&ip=192.168.1.111`
```json
 {
       "customerCarPlate": "皖A12346",
       "customerName": "梁伟",
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
       "description": null,
       "district":1
   }
```
- 返回示例：
```
{
    "status": "SUCCESS",
    "data": {
        "appId": "wxd5a553c228118fca",
        "partnerId": "1489500492",
        "prepayId": "wx20171215192443b4216f455f0108954480",
        "pack": "Sign=WXPay",
        "nonceStr": "44d213eb8d3140238cd97e77950b70ac",
        "timestamp": "1513337082",
        "sign": "3AA0839C5DA6D414D04E975B621A6465",
        "tradeId": "201712151924415203048",
        "result": "SUCCESS"
    }
}
```
## 6.5 道路查询接口

### 6.5.1 根据路段ID获得路段信息


- 功能描述：`获取指定路段的信息`

- 调用场景：`客户在购买月票时获取指定路段的信息(路段id、路段名、月票剩余数量、月票单价)`

- 请求地址：`http://domain/customer/roadSections/{id}？access_token&startMonth&endMonth`

- 请求动作：`GET`

- 请求示例：`http://localhost:8080/customer/roadSections/1000?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&startMonth=2017-12&endMonth=2017-12`

- 返回示例：
```json
{
    "status": "SUCCESS",
    "data": {
        "id": 1000,
        "name": "望江西路-创新大道",
        "unsoldMonthBillNum": 1000,
        "monthBillPrice": 10000,
        "parkingAreaName": "植保路"
    }
}
```
### 6.5.2 根据路段id获取所在的行政区

- 功能描述：`根据路段的id获取所在的行政区`

- 请求地址：`http://domain/customer/districts/getDistrictByRoadSectionId？access_token&name`

- 请求动作：`GET`

- 请求示例：`http://localhost:8080/customer/districts/getDistrictByRoadSectionId?access_token=35293431-a0e5-40db-866c-3f46a26f3a0a&id=1000`

- 返回示例：
```
{
    "status": "SUCCESS",
    "data": "蜀山区"
}

```

## 6.6 区域查询接口

### 6.6.1 根据区名获得该区对应的ID

- 功能描述：`根据区名获得该区对应的ID`

- 请求地址：`http://domain/customer/districts/getId？access_token&name`

- 请求动作：`GET`

- 请求示例：`http://localhost:8080/customer/districts/getId?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&name=蜀山区`

- 返回示例：
```json
{
    "status": "SUCCESS",
    "data": 1002
}

```








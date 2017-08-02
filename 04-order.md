### 4.1 findDefaultPostWithParkings接口
- 功能描述: `查询当前登录用户所在的默认岗位以及他所负责的泊位和订单。`

- 请求地址: `http://domain/order/orders/findDefaultPostWithParkings`

- 请求动作: `GET`

- 请求示例: `http://domain/order/orders/findDefaultPostWithParkings?access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`

- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "postId": 1014,
        "parkings": [
            {
                "id": 1017,
                "code": "154140",
                "chargingStrategy": 1
            },
            {
                "id": 1018,
                "code": "154141",
                "chargingStrategy": 1
            },
            {
                "id": 1020,
                "code": "154142",
                "chargingStrategy": 1
            },
            {
                "id": 1021,
                "code": "154144",
                "chargingStrategy": 1
            }
        ],
        "orderSummaries": [
            {
                "id": 10000106,
                "status": 1,
                "carPlate": "皖A12345",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000107,
                "status": 1,
                "carPlate": "皖A12345",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000109,
                "status": 1,
                "carPlate": "皖A12345",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000111,
                "status": 1,
                "carPlate": "皖A12345",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000089,
                "status": 1,
                "carPlate": "皖A12345",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            }
        ]
    }
}
```


### 4.2 findDefaultPostSiblings接口
- 功能描述: `通过默认岗位id查询它所属路段的所有岗位`

- 请求地址: `http://domain/order/orders/findDefaultPostSiblings`

- 请求动作: `GET`

- 请求示例: `http://domain/order/orders/findDefaultPostSiblings?defaultPostId=1014&access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`

- 返回示例: 
```
{
    "status": "SUCCESS",
    "data": [
        {
            "name": "岗位1",
            "id": 1014
        },
        {
            "name": "岗位2",
            "id": 1015
        }
    ]
}

```



### 4.3 findAllParkingsByPost接口
- 功能描述: `通过岗位id查询该岗位下的所有泊位和订单`

- 请求地址: `http://domain/order/orders/findAllParkingsByPost`

- 请求动作: `GET`

- 请求示例: `http://domain/order/orders/findAllParkingsByPost?postId=1014&access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`

- 返回示例: 
```
{
    "status": "SUCCESS",
    "data": {
        "postId": 1014,
        "parkings": [
            {
                "id": 1017,
                "code": "154140",
                "chargingStrategy": 1
            },
            {
                "id": 1018,
                "code": "154141",
                "chargingStrategy": 1
            },
            {
                "id": 1020,
                "code": "154142",
                "chargingStrategy": 1
            },
            {
                "id": 1021,
                "code": "154144",
                "chargingStrategy": 1
            }
        ],
        "orderSummaries": [
            {
                "id": 10000105,
                "status": 1,
                "carPlate": "皖A12345",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000106,
                "status": 1,
                "carPlate": "皖A12345",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000107,
                "status": 1,
                "carPlate": "皖A12345",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000108,
                "status": 1,
                "carPlate": "皖A12345",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000109,
                "status": 1,
                "carPlate": "皖A12345",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000111,
                "status": 1,
                "carPlate": "皖A12345",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            }
        ]
    }
}
```


### 4.4 driveIn接口

- 功能描述: `车辆驶入，提交一个新的订单`

- 请求地址: `http://domain/order/orders/driveIn`

- 请求动作: `POST`

- 请求示例: `http://domain/order/orders/driveIn?access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`
```
{
    "carPlate":"皖A12345",
    "vehicleType":1,
    "parking":{"id":1017},
    "driveInEmployeeId":"1002",
    "driveInPosSn":"123",
    "payType":3
}
```
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "carPlate": "皖A12345",
        "parkingCode": "154140",
        "driveInPosSn": "123",
        "roadSectionName": "潜山路-怀宁路",
        "vehicleType": 1,
        "driveInEmployeeId": 1002,
        "createDate": "2017-07-19 09:26:08",
        "arrears": 7000
    }
}
```



### 4.5 driveOut接口

- 功能描述: `车辆驶出，通过订单id更新订单`

- 请求地址: `http://domain/order/orders/driveOut`

- 请求动作: `PUT`

- 请求示例: `http://domain/order/orders/driveOut?id=10000119&access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`
```
{
  "fee":4000,
  "payType":1,
  "completeDate":"2017-07-13 15:13:14",
  "driveOutEmployeeId":"1002",
  "driveOutPosSn":"123",
  "status":3
} 
```

- 返回示例:
    - 当订单状态为进行中时
    ```
    {
        "status": "SUCCESS",
        "data": {
            "driveOutEmployeeId": 1002,
            "parkingCode": "154140",
            "roadSectionName": "潜山路-怀宁路",
            "vehicleType": 1,
            "completeDate": "2017-07-13 15:13:14",
            "fee": 4000,
            "payType": 1
        }
    }
    ```
    - 当订单状态为待确认、完成或欠费时
    ```
    {
        "status": "FAILURE",
        "error": "车辆已驶出，订单已完成"
    }
    ```



### 4.6 uploadOrderVehicleImage接口

- 功能描述: `上传车辆图片信息`

- 请求地址: `http://domain/zuul/order/orders/uploadOrderVehicleImage`

- 请求动作: `PUT`

- 请求示例: `http://domain/zuul/order/orders/uploadOrderVehicleImage?id=10000122&access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`
![Markdown](http://i1.buimg.com/1949/84c15df0a215c259.png)

- 返回示例:
```
{
    "status": "SUCCESS"
}
```

- 注意: `当MultipartFile file接收上传的文件时，如果文件太大，file为空。解决方法：在访问地址中添加/zuul/*，让请求越过DispatcherServlet,从而避免对MultipartFile文件进行处理。但是我们在测试的过程中用大小为4KB的图片上传仍然出现了该问题，因此建议在上传任何MultipartFile在url中加上/zuul/*`




### 4.7 /{id}/image接口
- 功能描述: `获取车辆图片`

- 请求地址: `http://domain/order/orders/{id}/image`

- 请求动作: `GET`

- 请求示例: `http://domain/order/orders/10000096/image?access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`

- 返回示例: 

    ![Markdown](http://i2.kiimg.com/1949/7c84a20ddd1f1eaa.png)


### 4.8 查询全部订单信息接口
- 功能描述: `查询全部订单信息`

- 请求地址: `http://domain/order/orders`

- 请求动作: `GET`

- 请求示例: `http://domain/order/orders?access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`

- 返回示例: 

### 4.9 根据订单id、车牌号、泊位编号查询订单接口

- 功能描述：根据订单id、车牌号、泊位编号查询订单接口

- 请求地址：`http://localhost:8080/order/orders/query?access_token&carPlate&id&parkingCode`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/orders/query?access_token=5d780ca8-fc23-4bfd-8513-d64b517e9d63&carPlate=皖A12375&id=10000181&parkingCode=133002`

   - 备注：参数可以缺省。

- 返回示例：
```aidl
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 10000114,
                "carPlate": "皖A59436",
                "vehicleType": 1,
                "parking": {
                    "id": 1006,
                    "code": "133002",
                    "chargingStrategyId": 1000,
                    "post": {
                        "id": 1002,
                        "name": "1号岗",
                        "roadSection": {
                            "id": 1002,
                            "name": "金寨路-桐城路 南侧",
                            "parkingArea": {
                                "id": 1003,
                                "code": "3401030001",
                                "name": "庐江路",
                                "district": "庐阳区"
                            }
                        }
                    }
                },
                "driveInEmployee": {
                    "id": 1002,
                    "name": "张齐健",
                    "phoneNum": "13999999999",
                    "defaultPost": {
                        "id": 1002,
                        "name": "1号岗",
                        "roadSection": {
                            "id": 1002,
                            "name": "金寨路-桐城路 南侧",
                            "parkingArea": {
                                "id": 1003,
                                "code": "3401030001",
                                "name": "庐江路",
                                "district": "庐阳区"
                            }
                        }
                    }
                },
                "driveOutEmployee": {
                    "id": 1002,
                    "name": "张齐健",
                    "phoneNum": "13999999999",
                    "defaultPost": {
                        "id": 1002,
                        "name": "1号岗",
                        "roadSection": {
                            "id": 1002,
                            "name": "金寨路-桐城路 南侧",
                            "parkingArea": {
                                                            "id": 1003,
                                                            "code": "3401030001",
                                                            "name": "庐江路",
                                                            "district": "庐阳区"
                                                        }
                                                    }
                                                }
                                            },
                                            "driveInPosSn": "000000000000000",
                                            "driveOutPosSn": "862401030000092",
                                            "completeDate": "2017-08-02 09:59:50",
                                            "fee": 2300,
                                            "payType": 1,
                                            "status": 3,
                                            "createdBy": "wyf",
                                            "createdDate": {
                                                "epochSecond": 1501639190,
                                                "nano": 758000000
                                            },
                                            "lastModifiedBy": "wyf",
                                            "lastModifiedDate": {
                                                "epochSecond": 1501660677,
                                                "nano": 3000000
                                            }
                                        }
                                    ],
                                    "totalPages": 1,
                                    "totalElements": 1,
                                    "last": true,
                                    "first": true,
                                    "sort": null,
                                    "numberOfElements": 1,
                                    "size": 20,
                                    "number": 0
                                }
                            }
```
     
        

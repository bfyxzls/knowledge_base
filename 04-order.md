## 4.1 订单信息访问接口
### 4.1.1 findDefaultPostWithParkings接口
- 功能描述: 查询当前登录用户所在的默认岗位以及他所负责的泊位和订单。

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


### 4.1.2 findDefaultPostSiblings接口
- 功能描述: 通过默认岗位id查询它所属路段的所有岗位

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



### 4.1.3 findAllParkingsByPost接口
- 功能描述: 通过岗位id查询该岗位下的所有泊位和订单

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


### 4.1.4 driveIn接口

- 功能描述: 车辆驶入，提交一个新的订单

- 请求地址: `http://domain/order/orders/driveIn?access_token`

- 请求动作: `POST`

- 请求示例: `http://domain/order/orders/driveIn?access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`
```
{
    "carPlate":"皖A12345",
    "vehicleType":1,
    "parkingId":1017,
    "driveInEmployeeId":1002,
    "driveInPosSn":"123",
    "isMonthBill":false
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



### 4.1.5 driveOut接口

- 功能描述: 车辆驶出，通过订单id更新订单

- 请求地址: `http://domain/order/orders/driveOut`

- 请求动作: `PUT`

- 请求示例: `http://domain/order/orders/driveOut?id=10000119&access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`
```
{
  "fee":4000,
  "payType":1,
  "completeDate":"2017-07-13 15:13:14",
  "driveOutEmployeeId":1002,
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
        "roadSectionName": "岳西路-长江西路",
        "vehicleType": 1,
        "createdDate": "2017-08-04 08:41:43",
        "completeDate": "2017-07-13 15:13:14",
        "fee": 4000,
        "payType": 1,
        "isMonthBill": false,
        "arrears": null
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



### 4.1.6 uploadOrderVehicleImage接口

- 功能描述: 上传车辆图片信息

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

- 注意: 当MultipartFile file接收上传的文件时，如果文件太大，file为空。解决方法：在访问地址中添加`/zuul/*`，让请求越过DispatcherServlet,从而避免对MultipartFile文件进行处理。但是我们在测试的过程中用大小为4KB的图片上传仍然出现了该问题，因此建议在上传任何MultipartFile在url中加上`/zuul/*`




### 4.1.7 /{id}/image接口
- 功能描述: 获取车辆图片

- 请求地址: `http://domain/order/orders/{id}/image`

- 请求动作: `GET`

- 请求示例: `http://domain/order/orders/10000096/image?access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`

- 返回示例: 

    ![Markdown](http://i2.kiimg.com/1949/7c84a20ddd1f1eaa.png)


### 4.1.8 查询全部订单信息接口
- 功能描述: 查询全部订单信息

- 请求地址: `http://domain/order/orders`

- 请求动作: `GET`

- 请求示例: `http://domain/order/orders?access_token=9e245715-aef8-47ff-bf4a-3030d6258e03`

- 返回示例: 

### 4.1.9 根据订单id、车牌号、泊位编号查询订单接口

- 功能描述：根据订单id、车牌号、泊位编号查询订单接口

- 请求地址：`http://domain/order/orders/query?access_token&carPlate&id&parkingCode`

- 请求动作: `GET`

- 请求示例：`http://domain/order/orders/query?id=10000114&access_token=e10c62ae-3bc8-4938-bdbe-1465bf25c12a`

   - 备注：参数可以缺省。

- 返回示例：
```
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
### 4.1.10  appDriveOutConfirmed接口
- 功能描述: App端缴费并驶离，pos端确认驶离

- 请求地址: `http://domain/order/orders/appDriveOutConfirmed?id&access_token`

- 请求动作: `PUT`

- 请求示例: `http://domain/order/orders/appDriveOutConfirmed?id=10000260&access_token=325019f8-9b62-499b-b392-7624ca30a00e`
    - body:
```
{
	"driveOutEmployeeId":1002,
	"driveOutPosSn":"123",
	 "status":3
}
```
- 返回示例: 
```
{
    "status": "SUCCESS",
    "data": {
        "driveOutEmployeeId": 1002,
        "parkingCode": "154140",
        "roadSectionName": "岳西路-长江西路",
        "vehicleType": 1,
        "createdDate": "2017-08-04 20:01:45",
        "completeDate": "2017-08-03 17:26:49",
        "fee": 222,
        "payType": 1,
        "isMonthBill": false,
        "arrears": null
    }
}
```
### 4.1.11 appDriveOutWithFeeConfirmed
- 功能描述: App端缴费未驶离，pos端缴费后驶离确认

- 请求地址: `http://domain/order/orders/appDriveOutWithFeeConfirmed?id&access_token`

- 请求动作: `PUT`

- 请求示例: `http://domain/order/orders/appDriveOutWithFeeConfirmed?id=10000261&access_token=09b890b3-1685-4cd4-a084-af6ac51d115e`
    - body:
```
{
  "fee":333,
  "payType":1,
  "completeDate":"2017-07-13 15:13:14",
  "driveOutEmployeeId":1002,
  "driveOutPosSn":"123",
  "status":3
} 
```
- 返回示例: 
```
{
    "status": "SUCCESS",
    "data": {
        "driveOutEmployeeId": 1002,
        "parkingCode": "154140",
        "roadSectionName": "岳西路-长江西路",
        "vehicleType": 1,
        "createdDate": "2017-08-04 21:16:16",
        "completeDate": "2017-07-13 15:13:14",
        "fee": 333,
        "payType": 1,
        "isMonthBill": false,
        "arrears": null
    }
}
```
### 4.1.12 getHistoryFeeRecord接口
- 功能描述: 待确认状态下二次缴费计算应缴费用

- 请求地址: `http://domian/order/orders/getHistoryFeeRecord?id&access_token`

- 请求动作: `GET`

- 请求示例: `http://domain/order/orders/getHistoryFeeRecord?id=10000261&access_token=09b890b3-1685-4cd4-a084-af6ac51d115e`

- 返回示例: 
```
{
    "status": "SUCCESS",
    "data": 111
}
```
### 4.1.13 getParkingState接口
- 功能描述: 通过Pos机查询当前泊位的停车状态信息

- 请求地址: `http://domian/order/orders/getParkingState?parkingCode&access_token`

- 请求动作: `GET`

- 请求示例: `http://domain/order/orders/getParkingState?access_token=82dae454-5c86-404f-93d1-4cdae1775cff&parkingCode=133000`

- 返回示例: 
```
{
    "status": "SUCCESS",
    "data": {
        "parkingCode": "133000",
        "status": "空闲",
        "carPlate": null,
        "roadSectionName": null,
        "vehicleType": null,
        "driveInEmployeeName": null,
        "driveInPosSn": null,
        "createdDate": null
    }
}
```
### 4.1.14 AppPayArrearsFee接口
- 功能描述: 补缴欠费订单

- 请求地址: `http://domian/order/orders/appPayArrearsFee?appPayArrearsOrderCommands&access_token`

- 请求动作: `PUT`

- 请求示例: `http://domain/order/orders/appPayArrearsFee?access_token=82dae454-5c86-404f-93d1-4cdae1775cff`

- 请求实体：
'''
[
      {
                "orderId": 10000272,
                "payType":4,
                "payTime": "2017-08-13 19:21:21",
                "arrearsFee": 200
            },
            {
                "orderId": 10000281,
                "payType":4,
                "payTime": "2017-08-13 15:13:14",
                "arrearsFee": 199
            }
]
'''
- 返回示例:
'''
{
    "status": "SUCCESS",
    "data": "补缴欠费成功"
}
'''
 ### 4.1.15 PosPayArrearsFee接口
 - 功能描述: 补缴欠费订单
 
 - 请求地址: `http://domian/order/orders/posPayArrearsFee?appPayArrearsOrderCommands&access_token`
 
 - 请求动作: `PUT`
 
 - 请求示例: `http://domain/order/orders/posPayArrearsFee?access_token=82dae454-5c86-404f-93d1-4cdae1775cff`
 
 - 请求实体：
 '''
 [
       {
                 "orderId": 10000272,
                 "payType":4,
                 "payTime": "2017-08-13 19:21:21",
                 "arrearsFee": 200
             },
             {
                 "orderId": 10000281,
                 "payType":4,
                 "payTime": "2017-08-13 15:13:14",
                 "arrearsFee": 199
             }
 ]
 '''
 - 返回示例:
 '''
 {
     "status": "SUCCESS",
     "data": {
         "numOfArrearsOrder": 2,
         "totalFee": 399
     }
 }
 '''
## 4.2 APP驶出接口
### 4.2.1 appDriveOut接口
    
- 功能描述：用户对某个订单缴费驶离

- 请求地址：`http://domain/order/app/orders/driveOut?access_token&orderId`

- 请求动作: `PUT`

- 请求示例：`http://domain/order/app/orders/driveOut?access_token=4abb5a74-a913-4c83-8de8-bdd074812507&orderId=10000215`

    - Body：
```
{
	"payTime":"2017-08-03 17:26:49",
	"payType":1,
	"fee":222
}
```
- 返回示例：    
```
{
    "status": "SUCCESS",
    "data": {
        "parkingCode": "154140",
        "roadSectionName": "岳西路-长江西路",
        "vehicleType": 1,
        "createdDate": "2017-08-04 09:01:36",
        "payTime": "2017-08-03 17:26:49",
        "fee": 222,
        "payType": 1,
        "isMonthBill": false,
        "arrears": null
    }
}
```
        

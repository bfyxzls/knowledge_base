## 4.1 订单信息访问接口（OrderController）
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
    "vehicleType":"01",
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
        "vehicleType": "01",
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

-  当订单状态为待确认、完成或欠费时
     ```

     ```
    {
        "status": "FAILURE",
        "error": "车辆已驶出，订单已完成"
    }
    ​```



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

### 4.1.9 查询订单接口

- 功能描述：查询订单
- 请求动作: `GET`
- 请求地址：`http://domain/order/orders/query?access_token`
- 参数位置：`Request Parameter`
- 请求参数：
  - `id`：`订单id`
  - `carPlate`：`车牌号`
  - `parkingCode`：`泊位编码`
  - `statuses`：`订单状态（可多个，逗号隔开）`
  - `parkingStartTime`：`停车开始时间`
  - `parkingEndTime`：`停车结束时间`
  - `roadSectionId`：`路段id`
  - `district`：`区`
  - `driveInEmployeeId`：`驶入员工id`
  - `driveInPosSn`：`驶入pos机`
  - `driveInEmployeeName`：`驶入员工姓名`
  - `driveOutEmployeeId`：`驶出员工id`
  - `driveOutPosSn`：`驶出pos机`
  - `driveOutEmployeeName`：`驶出员工姓名`
  - `page`：`当前页码，从0开始`
  - `size`：`条数`
- 请求示例：`localhost:8080/order/orders/query?access_token=9d3af5fd-3e33-4d18-bafd-1317302bf826&parkingStartTime=2017-08-01 22:22:22&parkingEndTime=2018-08-08 08:08:08`
  - 备注：参数可以缺省。
- 返回示例：

```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 10000273,
                "carPlate": "皖A12345",
                "parkingCode": "154140",
                "roadSectionName": "岳西路-长江西路",
                "district": "蜀山区",
                "driveInTime": "2017-08-01 19:23:01",
                "driveOutTime": "2017-08-02 15:13:14",
                "driveOutEmployeeName": "赵朋飞",
                "driveOutEmployeePhoneNum": "7777777",
                "driveOutPosSn": "123",
                "fee": 0,
                "arrearsFee": 0,
                "status": 3,
                "arrearsPaidTime": null
            },
            ...
        ],
        "totalElements": 64,
        "last": false,
        "totalPages": 4,
        "size": 20,
        "number": 0,
        "first": true,
        "sort": null,
        "numberOfElements": 20
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
### 4.1.11 appDriveOutWithFeeConfirmed接口
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
    "data": {
        "feeAlreadyPaid": 200
    }
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

### 4.1.15 PosPayArrearsFee接口
-  功能描述: 补缴欠费订单

-  请求地址: `http://domian/order/orders/posPayArrearsFee?appPayArrearsOrderCommands&access_token`

-  请求动作: `PUT`

-  请求示例: `http://domain/order/orders/posPayArrearsFee?access_token=82dae454-5c86-404f-93d1-4cdae1775cff`

-  请求实体：
```
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
```

- 返回示例:
```
    {
     "status": "SUCCESS",
     "data": {
         "numOfArrearsOrder": 2,
         "totalFee": 399
     }
    }
```

### 4.1.16 obtainParkingOrderDetails接口
- 功能描述：管理员查看某个订单的详细信息

- 请求地址：http://localhost:8080/order/orders/{}/obtainParkingOrderDetails?access_token

- 请求动作：GETid

- 请求示例：http://localhost:8080/order/orders/10000313/obtainParkingOrderDetails?access_token=a57c7550-8538-47ac-9056-ac5c0f71b80d

- 返回示例：
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "id": 10000313,
        "parkingCode": "154140",
        "period": -40448,
        "vehicleType": "1",
        "status": 3,
        "carPlateNum": "皖A12345",
        "district": "蜀山区",
        "roadSectionName": "岳西路-长江西路",
        "chargingStrategyDescription": "前15分钟免费，00:00-07:30 免费；07:30-21:30 按时收费（0-30分钟6.0元/30分钟；30分钟以后4.0元/30分钟）；21:30-23:59 免费。",
        "driveInEmpDto": {
            "name": "赵朋飞",
            "id": 1002,
            "phoneNum": "7777777",
            "posSn": "123",
            "operationDate": "2017-08-10 17:22:04"
        },
        "driveOutEmpDto": {
            "name": "赵朋飞",
            "id": 1002,
            "phoneNum": "7777777",
            "posSn": "123",
            "operationDate": "2017-07-13 15:13:14"
        },
        "feeShouldPay": 200,
        "feeActuallyPay": 200,
        "arrearsFee": null,
        "arrearsPaidDate": null,
        "arrearsOrderGeneratedDate": null
    }
}
```
 ### 4.1.17 changeCarPlate接口
- 功能描述：修改订单的车牌

- 请求地址：http://localhost:8080/order/orders/{id}/changeCarPlate?access_token&carPlate

- 请求动作：put

- 请求示例：http://localhost:8080/order/orders/10000283/changeCarPlate?access_token=8f3a8e76-fd86-49c6-9bf2-5f42563c2486&carPlate=皖B12345

- 返回示例：
 ```
{
    "status": "SUCCESS",
    "data": {
        "id": 10000283,
        "carPlate": "皖B12345",
        "vehicleType": "1",
        "parking": {
            "id": 1017,
            "code": "154140",
            "chargingStrategyId": 1000,
            "post": {
                "id": 1014,
                "name": "岗位1",
                "roadSection": {
                    "id": 1021,
                    "name": "岳西路-长江西路",
                    "parkingArea": {
                        "id": 1037,
                        "code": "700000",
                        "name": "岳西路停车场",
                        "district": "蜀山区"
                    }
                }
            }
        },
        "driveInEmployee": {
            "id": 1002,
            "name": "赵朋飞",
            "phoneNum": "7777777",
            "defaultPost": {
                "id": 1014,
                "name": "岗位1",
                "roadSection": {
                    "id": 1021,
                    "name": "岳西路-长江西路",
                    "parkingArea": {
                        "id": 1037,
                        "code": "700000",
                        "name": "岳西路停车场",
                        "district": "蜀山区"
                    }
                }
            }
        },
        "driveOutEmployee": {
            "id": 1002,
            "name": "赵朋飞",
            "phoneNum": "7777777",
            "defaultPost": {
                "id": 1014,
                "name": "岗位1",
                "roadSection": {
                    "id": 1021,
                    "name": "岳西路-长江西路",
                    "parkingArea": {
                        "id": 1037,
                        "code": "700000",
                        "name": "岳西路停车场",
                        "district": "蜀山区"
                    }
                }
            }
        },
        "driveInPosSn": "123",
        "driveOutPosSn": "123",
        "completeDate": 1499929994000,
        "arrearsPaidDate": null,
        "fee": 0,
        "arrearsFee": 0,
        "isMonthBill": true,
        "status": 3,
        "parkingOrderFeeRecords": [
            {
                "id": 10000092,
                "payType": 1,
                "fee": 0,
                "payTime": "2017-07-13 15:13:14",
                "isInvoiceIssued": false,
                "employeeId": 1002,
                "employeeName": "赵朋飞",
                "phoneNum": "7777777",
                "district": "蜀山区"
            }
        ],
        "createdBy": "wyf",
        "createdDate": 1502281079717,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1502845810595,
        "onParking": false,
        "toBeConfirmed": false,
        "lastFeeRecord": {
            "id": 10000092,
            "payType": 1,
            "fee": 0,
            "payTime": "2017-07-13 15:13:14",
            "isInvoiceIssued": false,
            "employeeId": 1002,
            "employeeName": "赵朋飞",
            "phoneNum": "7777777",
            "district": "蜀山区"
        }
    }
}
 ```
## 4.2 APP端操作订单接口（AppOrderController）
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
### 4.2.2 AppPayArrearsFee接口
- 功能描述: 补缴欠费订单

- 请求地址: `http://domain/order/app/orders/payArrearsFee`

- 请求动作: `PUT`

- 请求示例: `http://192.168.1.18:8080/order/app/orders/payArrearsFee?access_token`

- 请求实体：
```
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
```
- 返回示例:
```
  {
    "status": "SUCCESS",
    "data": "补缴欠费成功"
  }
```

### 4.2.3 getVehicleFeeStats接口

- 功能描述：按车牌统计当前客户的待支付和待补缴订单数量

- 请求地址：`http://192.168.1.18:8080/order/app/orders/getVehicleFeeStats`

- 请求动作：`GET`

- 请求示例：`http://192.168.1.18:8080/order/app/orders/getVehicleFeeStats?access_token=1398a422-504a-4e95-8531-52cc0f5ebcc4&carPlates=皖A12345`

- 返回示例：
```$xslt
{
    "status": "SUCCESS",
    "data": [
        {
            "carPlate": "皖A12345",
            "numOfArrears": 3,
            "numOfCurrentFee": 16
        }
    ]
}
```

## 4.3 统计接口

### 4.3.1 countEmployeeTodayStats接口

- 功能描述：查询员工当日收费统计

- 请求地址：`http://domain/order/stats/{employeeId}/today?access_token`

- 请求动作: `GET`

- 请求示例：`http://domain/order/stats/11/today?access_token=4abb5a74-a913-4c83-8de8-bdd074812507`

- 返回示例：
```$xslt
{
      "status": "SUCCESS",
      "data": {
          "employeeId": 1001,
          "employeeName": "佘能斌",
          "incomeStats": {
              "num": 0,
              "sum": 0
          },
          "arrearsStats": {
              "num": 0,
              "sum": 0
          },
          "arrearsPaidStats": {
              "num": 0,
              "sum": 0
          },
          "printTime": "2017-08-15 09:08:27"
      }
  }
```
### 4.3.2 countParkingOrders接口

- 功能描述：统计当日订单信息

- 请求地址：`http://domain/order/stats/countParkingOrders?access_token=1398a422-504a-4e95-8531-52cc0f5ebcc4&roadSectionId=1021`

- 请求动作: `GET`

- 请求示例：`http://domain/order/stats/countParkingOrders?access_token=1398a422-504a-4e95-8531-52cc0f5ebcc4&roadSectionId=1021`

- 返回示例：
```
{
    "status": "SUCCESS",
    "data": {
        "allParkingOrdersCount": 24,
        "completeParkingOrdersCount": 5,
        "arrearsParkingOrdersCount": 1,
        "freeParkingOrdersCount": 2
    }
}
```


## 4.4 车辆信息接口

### 4.4.1 getParkingRecords接口

- 功能描述：根据车牌号查询停车记录

- 请求地址：`http://domain/order/vehicles/{carPlate}/parkingRecords?access_token`

- 请求动作: `GET`

- 请求示例：`http://domain/order/vehicles/皖A12345/parkingRecords?access_token=4abb5a74-a913-4c83-8de8-bdd074812507`
    - 注意事项： 车牌中的汉字须先进行url编码后方可放入url中作参数传递

- 返回示例：

```$xslt
{
      "status": "SUCCESS",
      "data": {
          "employeeId": 1001,
          "employeeName": "佘能斌",
          "incomeStats": {
              "num": 0,
              "sum": 0
          },
          "arrearsStats": {
              "num": 0,
              "sum": 0
          },
          "arrearsPaidStats": {
              "num": 0,
              "sum": 0
          },
          "printTime": "2017-08-15 08:34:15"
      }
  }
```

### 4.4.2 countArrears接口

- 功能描述：按车牌计算欠费笔数和金额

- 请求地址：`http://domain/order/vehicles/{carPlate}/countArrears?access_token`

- 请求动作: `GET`

- 请求示例：`http://domain/order/vehicles/皖A12345/countArrears?access_token=4abb5a74-a913-4c83-8de8-bdd074812507`
    - 注意事项： 车牌中的汉字须先进行url编码后方可放入url中作参数传递

- 返回示例：
```
  {
      "status": "SUCCESS",
      "data": {
          "carPlate": "皖A12345",
          "sumOfArrears": 0,
          "numOfArrears": 0
      }
  }
```
### 4.4.3 getArrears接口

- 功能描述：按车牌计算欠费笔数和金额

- 请求地址：`http://domain/order/vehicles/{carPlate}/arrears?access_token&page&size`

- 请求动作: `GET`

- 请求示例：`http://domain/order/vehicles/皖A12345/arrears?access_token=4abb5a74-a913-4c83-8de8-bdd074812507&page=1&size=10`
    - 注意事项： 车牌中的汉字须先进行url编码后方可放入url中作参数传递

- 返回示例：

  ```json
  {
      "status": "SUCCESS",
      "data": {
          "content": [
              {
                  "id": 10000269,
                  "createdDate": "2017-08-09 19:11:15",
                  "completeDate": "2017-07-13 15:13:14",
                  "arrearsFee": 0,
                  "roadSectionName": "岳西路-长江西路"
              },
              {
                  "id": 10000270,
                  "createdDate": "2017-08-09 19:13:29",
                  "completeDate": "2017-07-13 15:13:14",
                  "arrearsFee": 0,
                  "roadSectionName": "岳西路-长江西路"
              },
              {
                  "id": 10000271,
                  "createdDate": "2017-08-09 19:15:00",
                  "completeDate": "2017-07-13 15:13:14",
                  "arrearsFee": 0,
                  "roadSectionName": "岳西路-长江西路"
              },
              {
                  "id": 10000305,
                  "createdDate": "2017-08-10 16:51:56",
                  "completeDate": "2017-07-13 15:13:14",
                  "arrearsFee": null,
                  "roadSectionName": "岳西路-长江西路"
              },
              {
                  "id": 10000314,
                  "createdDate": "2017-08-10 17:23:49",
                  "completeDate": "2017-07-13 15:13:14",
                  "arrearsFee": 200,
                  "roadSectionName": "岳西路-长江西路"
              }
          ],
          "totalElements": 5,
          "last": true,
          "totalPages": 1,
          "size": 20,
          "number": 0,
          "first": true,
          "sort": null,
          "numberOfElements": 5
      }
  }
  ```
## 4.5 APP端获取车辆信息接口
### 4.5.1 getArrearsParkingOrder接口
- 功能描述：获取车辆的欠费订单

- 请求地址：`http://domain/order/app/vehicles/{carPlate}/arrears`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/app/vehicles/%e7%9a%96A12345/arrears?access_token`
    - 注意事项： 车牌中的汉字须先进行url编码后方可放入url中作参数传递

- 返回示例：
 ```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "orderId": 10000271,
                "roadSectionName": "岳西路-长江西路",
                "parkingAreaName": "岳西路停车场",
                "category": "路边停车",
                "createdDate": "2017-08-09 19:15:00",
                "completeDate": "2017-07-13 15:13:14",
                "arrearsFee": 0
            },
            {
                "orderId": 10000270,
                "roadSectionName": "岳西路-长江西路",
                "parkingAreaName": "岳西路停车场",
                "createdDate": "2017-08-09 19:13:29",
                "completeDate": "2017-07-13 15:13:14",
                "arrearsFee": 0
            },
            {
                "orderId": 10000269,
                "roadSectionName": "岳西路-长江西路",
                "parkingAreaName": "岳西路停车场",
                "createdDate": "2017-08-09 19:11:15",
                "completeDate": "2017-07-13 15:13:14",
                "arrearsFee": 0
            },
            {
                "orderId": 10000305,
                "roadSectionName": "岳西路-长江西路",
                "parkingAreaName": "岳西路停车场",
                "createdDate": "2017-08-10 16:51:56",
                "completeDate": "2017-07-13 15:13:14",
                "arrearsFee": 0
            },
            {
                "orderId": 10000314,
                "roadSectionName": "岳西路-长江西路",
                "parkingAreaName": "岳西路停车场",
                "createdDate": "2017-08-10 17:23:49",
                "completeDate": "2017-07-13 15:13:14",
                "arrearsFee": 200
            }
        ],
        "totalElements": 5,
        "last": true,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 5
    }
}
 ```
### 4.5.2 getParkingRecord接口
- 功能描述：获得车辆停车记录

- 请求地址：`http://domain/order/app/vehicles/{carPlate}/parkingRecords`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/app/vehicles/%e7%9a%96A12345/parkingRecords?access_token`

- 返回示例：
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "createdDate": "2017-08-03 17:26:49",
                "completeDate": "2017-08-03 17:26:49",
                "period": 0,
                "roadSectionName": "岳西路-长江西路",
                "parkingAreaName": "岳西路停车场",
                "fee": 222,
                "status": 3
            },
            {
                "createdDate": "2017-08-03 17:26:49",
                "completeDate": "2017-08-03 17:26:49",
                "period": 0,
                "roadSectionName": "岳西路-长江西路",
                "parkingAreaName": "岳西路停车场",
                "fee": 0,
                "status": 3
            },
            {
                "createdDate": "2017-07-13 15:13:14",
                "completeDate": "2017-07-13 15:13:14",
                "period": 0,
                "roadSectionName": "岳西路-长江西路",
                "parkingAreaName": "岳西路停车场",
                "fee": 300,
                "status": 3
            },
            {
                "createdDate": "2017-07-13 15:13:14",
                "completeDate": "2017-07-13 15:13:14",
                "period": 0,
                "roadSectionName": "岳西路-长江西路",
                "parkingAreaName": "岳西路停车场",
                "fee": 0,
                "status": 3
            }
        ],
        "totalElements": 40,
        "last": false,
        "totalPages": 2,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 20
    }
}
```

### 4.5.3 getPaymentRecord接口
- 功能描述：获得车辆收费记录

- 请求地址：`http://domain/order/app/vehicles/{carPlate}/paymentRecords`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/app/vehicles/%e7%9a%96A12345/paymentRecords?access_token`

- 返回示例：
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "carPlate": "皖A12345",
                "category": "路边停车",
                "completeDate": "2017-08-03 17:26:49",
                "fee": 222,
                "period": -8770,
                "appPayTypes": [
                    1
                ]
            }
        ],
        "totalElements": 40,
        "last": false,
        "totalPages": 2,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 20
    }
}
```

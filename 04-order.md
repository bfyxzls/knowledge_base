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
        "postName": "岗位1",
        "roadSectionId": 1021,
        "roadSectionName": "岳西路-长江西路",
        "parkingAreaName":"长江西路"
        "district": "蜀山区",
        "employeeId": 1001,
        "employeeName": "佘能斌",
        "employeePhoneNum": "18621061991",
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
                “vehicleType”: "01",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000107,
                "status": 1,
                "carPlate": "皖A12345",
                “vehicleType”: "01",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000109,
                "status": 1,
                "carPlate": "皖A12345",
                “vehicleType”: "01",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000111,
                "status": 1,
                "carPlate": "皖A12345",
                “vehicleType”: "01",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000089,
                "status": 1,
                "carPlate": "皖A12345",
                “vehicleType”: "01",
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
        "postName": "岗位1",
        "roadSectionId": 1021,
        "roadSectionName": "岳西路-长江西路",
        "parkingAreaName":"长江西路"
        "district": "蜀山区",
        "employeeId": 1001,
        "employeeName": "佘能斌",
        "employeePhoneNum": "18621061991",
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
                “vehicleType”: "01",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000107,
                "status": 1,
                "carPlate": "皖A12345",
                “vehicleType”: "01",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000109,
                "status": 1,
                "carPlate": "皖A12345",
                “vehicleType”: "01",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000111,
                "status": 1,
                "carPlate": "皖A12345",
                “vehicleType”: "01",
                "chargingStrategy": 1,
                "parkingCode": "154140",
                "parkingId": 1017
            },
            {
                "id": 10000089,
                "status": 1,
                "carPlate": "皖A12345",
                “vehicleType”: "01",
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
    	"id": "100001"
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
  "calculatedFee":4000,
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
        "createdDate": "2017-08-04 08:41:43",
        "completeDate": "2017-07-13 15:13:14",
        "fee": 4000,
        "payType": 1,
        "isMonthBill": false,
        "arrears": null,
        "carPlate": "皖A12345",
        "parkingPeriod":11
        }
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


### 4.1.8 查询订单接口

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

### 4.1.9  appDriveOutConfirmed接口
- 功能描述: App端缴费并驶离，pos端确认驶离
- 请求地址: `http://domain/order/orders/appDriveOutConfirmed?id&access_token`
- 请求动作: `PUT`
- 请求示例: `http://domain/order/orders/appDriveOutConfirmed?id=10000260&access_token=325019f8-9b62-499b-b392-7624ca30a00e`
- 请求参数（Request Body）:
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
    "data": "确认app端车辆驶出成功"
}
```
### 4.1.10 appDriveOutWithFeeConfirmed接口
- 功能描述: App端缴费未驶离，pos端缴费后驶离确认

- 请求地址: `http://domain/order/orders/appDriveOutWithFeeConfirmed?id&access_token`

- 请求动作: `PUT`

- 请求示例: `http://domain/order/orders/appDriveOutWithFeeConfirmed?id=10000261&access_token=09b890b3-1685-4cd4-a084-af6ac51d115e`
    - body:
```
{
  "fee":333,
  "calculatedFee":333,
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
        "arrears": null,
        "carPlate": "皖A12345",
        "parkingPeriod": 11
    }
}
```
### 4.1.11 getAppPaidFee接口
- 功能描述: pos机确认app支付时获取app支付的金额

- 请求地址: `http://domian/order/orders/getAppPaidFee?id&access_token`

- 请求动作: `GET`

- 请求示例: `http://domain/order/orders/getAppPaidFee?id=10000261&access_token=09b890b3-1685-4cd4-a084-af6ac51d115e`

- 返回示例: 
```
{
    "status": "SUCCESS",
    "data": {
        "feeAlreadyPaid": 200
    }
}
```
### 4.1.12 getParkingState接口
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


### 4.1.13 obtainParkingOrderDetails接口
- 功能描述：管理员查看某个订单的详细信息

- 请求地址：`http://localhost:8080/order/orders/{id}/obtainParkingOrderDetails`

- 请求动作：GET

- 请求示例：`http://localhost:8080/order/orders/10000313/obtainParkingOrderDetails?access_token=a57c7550-8538-47ac-9056-ac5c0f71b80d`

- 返回示例：
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "id": 10000313,
        "parkingCode": "154140",
        "period": -40448,
        "postId": 10001,
        "postName": "岗位一"
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
        "arrearsOrderGeneratedDate": null，
        "feeRecordDtos": {
            "payType": "2",
            "payTime": "2017-08-10 17:22:04",
            "fee": 200,
            "isInvoiceIssued": false
        }
    }
}
```
 ### 4.1.14 changeCarPlate接口
- 功能描述：修改订单的车牌

- 请求地址：`http://localhost:8080/order/orders/{id}/changeCarPlate?access_token&carPlate`

- 请求动作：put

- 请求示例：`http://localhost:8080/order/orders/10000283/changeCarPlate?access_token=8f3a8e76-fd86-49c6-9bf2-5f42563c2486&carPlate=皖B12345`

- 返回示例：
 ```
{
    "status": "SUCCESS",
    "data": "车牌更新成功"
}
 ```
### 4.1.15 obtainLastAppPayTime接口

- 功能描述：获取指定订单的最新手机支付时间

- 请求地址：`http://localhost:8080/order/orders/{id}/lastAppPayTime?access_token`

- 请求动作：`GET`

- 请求示例：`http://localhost:8080/order/orders/10000283/lastAppPayTime?access_token=8f3a8e76-fd86-49c6-9bf2-5f42563c2486`

- 返回示例：

  ```json
  {
      "status": "SUCCESS",
      "data": 1502441887000
  }
  ```


### 4.1.16 obtainParkingOrderDetailsForInvoice接口

- 功能描述：获取停车订单详细信息

- 请求地址：`http://localhost:8080/order/orders/{id}/obtainParkingOrderDetailsForInvoice?access_token`

- 请求动作：`GET`

- 请求示例：`http://localhost:8080/order/orders/10000283/obtainParkingOrderDetailsForInvoice?access_token=8f3a8e76-fd86-49c6-9bf2-5f42563c2486`

- 返回示例：

  ```json
  {
      "status": "SUCCESS",
      "data": {
          "vehicleType": "01",
          "carType": "皖B12345",
          "roadSectionName": "岳西路-长江西路",
          "parkingCode": "154140",
          "createdDate": "2017-08-28 17:04:41",
          "completeDate": "2017-08-28 17:13:14",
          "fee": 0,
          "payType": 1,
          "parkingPeriod": 8
      }
  }
  ```
### 4.1.17 obtainLatestDriveInReceipt接口

- 功能描述：pos机打印上一笔驶入凭证

- 请求地址：`http://domain/order/orders/obtainLatestDriveInReceipt?access_token`

- 请求动作：`GET`

- 请求示例：`http://localhost:8080/order/orders/obtainLatestDriveInReceipt?access_token=37c53656-1507-4cb8-a047-6bad018510c7`

- 返回示例：

  ```json
 {
    "status": "SUCCESS",
    "data": {
        "id": 10000227,
        "carPlate": "皖A12345",
        "parkingCode": "1000004",
        "driveInPosSn": "123",
        "roadSectionName": "潜山路-长江西路",
        "vehicleType": "01",
        "driveInEmployeeId": 1001,
        "createdDate": "2017-11-09 09:21:23",
        "arrears": 1000
    }
}
  ```
### 4.1.18 obtainTodayOrders接口

- 功能描述：收费员获取今日订单流水

- 请求地址：`http://domain/order/orders/obtainTodayOrders?access_token`

- 请求动作：`GET`

- 请求示例：`http://localhost:8080/order/orders/obtainTodayOrders?access_token=37c53656-1507-4cb8-a047-6bad018510c7`

- 返回示例：

  ```json
 {
    "status": "SUCCESS",
    "data": {
        "id": 10000227,
        "carPlate": "皖A12345",
        "parkingCode": "1000004",
        "driveInPosSn": "123",
        "roadSectionName": "潜山路-长江西路",
        "vehicleType": "01",
        "driveInEmployeeId": 1001,
        "createdDate": "2017-11-09 09:21:23",
        "arrears": 1000
    }
}
  ```
  

  ​

## 4.2 APP端操作订单接口（AppOrderController）

### 4.2.1 appObtainParkingOrderToBePaid接口

- 功能描述：App端根据订单id获取待支付订单信息

- 请求地址：`http://domain/order/app/orders/obtainParkingOrderToBePaid/{id}`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/app/orders/obtainParkingOrderToBePaid/10000300?access_token=99781806-157b-437c-8c30-f710bfa74d18`

- 返回示例：    
```
{
    "status": "SUCCESS",
    "data": {
        "carPlate": "皖A12345",
        "category": "路边停车",
        "roadSectionId": 10001,
        "roadSectionName": "岳西路-长江西路",
        "parkingAreaName": "岳西路停车场",
        "vehicleType": "02",
        "chargingStrategyId": 1000,
        "createdDate": "2017-08-10 14:50:32"
    }
}
```


### 4.2.2 getVehicleFeeStats接口

- 功能描述：按车牌统计当前客户的待支付和待补缴订单数量,并返回待支付订单id列表

- 请求地址：`http://domain/order/app/orders/getVehicleParkingOrderStats`

- 请求动作：`GET`

- 请求示例：`http://192.168.1.18:8080/order/app/orders/getVehicleParkingOrderStats?access_token=1398a422-504a-4e95-8531-52cc0f5ebcc4&carPlates=皖A12345`

- 返回示例：
```$xslt
{
    "status": "SUCCESS",
    "data": [
        {
            "carPlate": "皖A12345",
            "numOfArrears": 4,
            "numOfOnParking": 32,
            "parkingOrderIdsToBePaid": [
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
                10000432,
                10000433,
                10000434,
                10000435,
                10000277,
                10000282,
                10000284,
                10000286,
                10000298,
                10000299,
                10000306,
                10000419,
                10000422,
                10000423,
                10000424,
                10000425,
                10000426,
                10000427
            ]
        }
    ]
}
```

### 4.2.3 freeDriveOut接口

- 功能描述：app端用户免费驶离

- 请求地址：`http://domain/order/app/orders/{id}/freeDriveOut`

- 请求动作：`PUT`

- 请求示例：`http://192.168.1.18:8080/order/app/orders/1000023/freeDriveOut?access_token=1398a422-504a-4e95-8531-52cc0f5ebcc4&payType=4&calculatedFee=100&couponId=`

- 返回示例：

  ```json
  {
      "status": "SUCCESS"
    }
  ```

  ​

## 4.3 统计接口（StatsController）

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
        "freeParkingOrdersCount": 2,
        "arrearsPaidParkingOrdersCount": 0
        
    }
}
```
### 4.3.3 countTodayPay接口

- 功能描述：统计近日缴费

- 请求地址：`http://domain/order/stats/countTodayPay?access_token=1398a422-504a-4e95-8531-52cc0f5ebcc4&roadSectionId=1021`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/stats/countTodayPay?access_token=4d04bb9b-6941-4db0-a52f-a74e4f3b8219`

- 返回示例：
```
{
    "status": "SUCCESS",
    "data": {
        "numOfCashPay": 0,
        "numOfQRPay": 0,
        "numOfAppPay": 0,
        "totalNum": 0
    }
}
```
### 4.3.4 countTodayIncomeGroupByDistrict接口

- 功能描述：按区统计今日收入

- 请求地址：`http://domain/order/stats/countTodayIncomeGroupByDistrict?access_token`

- 请求动作: `GET`

- 请求示例：`http://domain/order/stats/countTodayIncomeGroupByDistrict?access_token=1398a422-504a-4e95-8531-52cc0f5ebcc4`

- 返回示例：

  ```JSON
  {
      "status": "SUCCESS",
      "data": [
          {
              "district": "庐阳区",
              "income": 87600
          }
      ]
  }
  ```
### 4.3.5 countTodayOrders接口

- 功能描述：统计今日订单量

- 请求地址：`http://domain/order/stats/countTodayOrders?access_token`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/stats/countTodayOrders?access_token=35b95947-6e0c-4291-964c-75af974fcd44`

- 返回示例：

  ```JSON
  {
      "status": "SUCCESS",
      "data": {
          "numOfFreeOrders": 0,
          "numOfChargedOrders": 0,
          "numOfArrearsOrders": 0,
          "numOfOnParkingOrders": 103,
          "arrearsPaidParkingOrdersCount": 0,
          "sumOfTodayOrders": 0
      }
  }
  ```


## 4.4 车辆信息接口（VehicleController）

### 4.4.1 getParkingRecords接口

- 功能描述：根据车牌号查询停车记录

- 请求地址：`http://domain/order/vehicles/{carPlate}/parkingRecords?access_token`

- 请求动作: `GET`

- 请求示例：`http://domain/order/vehicles/皖A12345/parkingRecords?access_token=4abb5a74-a913-4c83-8de8-bdd074812507&page=0&size=20&sort=createdDate,DESC`
    - 注意事项： 车牌中的汉字须先进行url编码后方可放入url中作参数传递

- 返回示例：

```$xslt
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "createdDate": "2017-09-05 12:52:06",
                "completeDate": null,
                "period": null,
                "roadSectionName": "岳西路-长江西路",
                "parkingAreaName": "岳西路停车场",
                "fee": null,
                "status": 1
            }
        ],
        "last": false,
        "totalElements": 78,
        "totalPages": 4,
        "size": 20,
        "number": 0,
        "first": true,
        "sort": [
            {
                "direction": "DESC",
                "property": "createdDate",
                "ignoreCase": false,
                "nullHandling": "NATIVE",
                "ascending": false,
                "descending": true
            }
        ],
        "numberOfElements": 20
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
### 4.4.3 obtainArrearsOrders接口

- 功能描述：按车牌查询欠费订单分页列表

- 请求地址：`http://domain/order/vehicles/{carPlate}/arrears?access_token&page&size`

- 请求动作: `GET`

- 请求示例：`http://domain/order/vehicles/皖A12345/arrears?access_token=4abb5a74-a913-4c83-8de8-bdd074812507&page=1&size=10&sort=createdDate,DESC`
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
                  "roadSectionName": "岳西路-长江西路",
                  "vehicleType": "02"
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
  
  
### 4.4.4 obtainArrearsOrdersWithOutPage接口

- 功能描述：按车牌查询欠费订单列表

- 请求地址：`http://domain/order/vehicles/{carPlate}/arrearsWithOutPage?access_token`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/vehicles/%e7%9a%96A12345/arrearsWithOutPage?access_token=cb5d69d3-ab15-4774-9ab9-fcf1afafb75d`
    - 注意事项： 车牌中的汉字须先进行url编码后方可放入url中作参数传递

- 返回示例：

 ```json
  {
    "status": "SUCCESS",
    "data": [
        {
            "id": 10000202,
            "createdDate": "2017-10-26 15:33:46",
            "completeDate": "2017-10-26 15:13:14",
            "arrearsFee": 1000,
            "roadSectionName": "潜山路-长江西路",
            "vehicleType": "01"
        }
    ]
}

```


### 4.4.5 isDiscount接口

- 功能描述：车辆类型判断、新能源车是否可享受优惠

- 请求地址：`localhost:8080/order/vehicles/check?access_token&carPlat`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/vehicles/localhost:8080/order/vehicles/check?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&carPlate=%e7%9a%96A12347`
    - 注意事项： 车牌中的汉字须先进行url编码后方可放入url中作参数传递

- 返回示例：

 ```json
{
    "status": "SUCCESS",
    "data": {
        "carPlate": "皖A12347",
        "isDiscount": true
    }
}

```
### 4.4.6 新增特殊车辆接口

- 功能描述：新增特殊车辆

- 请求地址：`localhost:8080/order/vehicles/special?access_token`

- 调用场景：`web端录入特殊车辆，报备的特殊车辆不收费`

- 请求动作: `POST`

- 请求示例：`http://localhost:8080/order/vehicles/special?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 请求实体：
```json
{
	"carPlate":"皖A11111",
    "ownerName":"gigigi",
    "ownerCompany":"bat",
    "ownerPhoneNum":"0986543211",
    "valid":true
}
```

- 返回示例：

 ```json
{
    "status": "SUCCESS"
}

```

### 4.4.7 新增新能源车接口

- 功能描述：`新增新能源车`

- 调用场景：`web端录入新能源车，报备的新能源车每天可享受两次一小时停车免费的优惠`


- 请求地址：`localhost:8080/order/vehicles/newEnergy?access_token`

- 请求动作: `POST`

- 请求示例：`http://localhost:8080/order/vehicles/newEnergy?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 请求实体：
```json
{
	"carPlate":"皖A00001",
    "ownerPhoneNum":"11234567809",
    "valid":true,
    "ownerCardId":"123456782287654321",
    "engineNum": "000",
    "vin": "000",
    "registerTime": "2017-12-13 18:00:00",
    "validDate" :"2018-12-14 00:00:00"
 }

```

- 返回示例：

 ```json
{
    "status": "SUCCESS"
}

```

### 4.4.8 更新特殊车辆接口

- 功能描述：`更新特殊车辆`

- 调用场景：`web端编辑特殊车辆信息`

- 请求地址：`localhost:8080/order/vehicles/special/{id}?access_token`

- 请求动作: `PUT`

- 请求示例：`http://localhost:8080/order/vehicles/special/32?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 请求实体：
```json
{
	"carPlate":"皖A11111",
    "ownerName":"gigi",
    "ownerCompany":"hfcb",
    "ownerPhoneNum":"12345678900",
    "valid":true
}

```

- 返回示例：

 ```json
{
    "status": "SUCCESS"
}
```

### 4.4.9 更新新能源车辆接口

- 功能描述：`更新新能源车车辆`

- 调用场景：`web端编辑新能源车信息`

- 请求地址：`localhost:8080/order/vehicles/newEnergy/{id}?access_token`

- 请求动作: `PUT`

- 请求示例：`http://localhost:8080/order/vehicles/newEnergy/33?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 请求实体：
```json
{
	"carPlate":"皖A00001",
    "ownerPhoneNum":"11234567809",
    "valid":true,
    "ownerCardId":"123456782287654321",
    "engineNum": "111",
    "vin": "111",
    "registerTime": "2017-12-13 18:00:00",
    "validDate" :"2019-12-14 00:00:00"
}
```

- 返回示例：
```json
{
    "status": "SUCCESS"
}
```

### 4.4.10 查询指定的特殊车辆接口

- 功能描述：`查询指定的特殊车辆`

- 调用场景：`web端查询特殊车辆详细信息`

- 请求地址：`localhost:8080/order/vehicles/sepcial/{id}?access_token`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/vehicles/special/30?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 返回示例：
```json
{
    "status": "SUCCESS",
    "data": {
        "id": 30,
        "carPlate": "皖A12345",
        "ownerName": "vivivi",
        "ownerCompany": "hfcb",
        "createdDate": 1513167338643,
        "createdBy": "wyf",
        "ownerPhoneNum": "12345678900",
        "valid": true
    }
}
```

### 4.4.11 查询指定的新能源车辆接口

- 功能描述：`查询指定的新能源车辆`

- 调用场景：`web端查询新能源车详细信息`

- 请求地址：`localhost:8080/order/vehicles/newEnergy/{id}?access_token`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/vehicles/newEnergy/31?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 返回示例：
```json
{
    "status": "SUCCESS",
    "data": {
        "id": 31,
        "carPlate": "皖A00000",
        "ownerPhoneNum": "01234567899",
        "valid": true,
        "ownerCardId": "123456789987654321",
        "engineNum": "000",
        "vin": "000",
        "registerTime": 1513159200000,
        "validDate": 1544716800000,
        "remark": "新能源车",
        "lastModifiedDate": 1513167401754
    }
}
```

### 4.4.12 条件查询特殊车辆的接口

- 功能描述：`根据车牌牌照、归属人，归属人手机号查找特殊车辆`

- 调用场景：`web端根据车牌牌照、归属人，归属人手机号查找特殊车辆`

- 请求地址：`localhost:8080/order/vehicles/special/query?carPlate&ownerName&ownerPhoneNum&access_token`
           `carPlate&ownerName&ownerPhoneNum是非必须的可以缺省`
- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/vehicles/special/query?carPlate=皖A12345&ownerName=vivivi&ownerPhoneNum=12345678900&access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 返回示例：
```json
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 30,
                "carPlate": "皖A12345",
                "ownerName": "vivivi",
                "ownerCompany": "hfcb",
                "createdDate": 1513167338643,
                "createdBy": "wyf",
                "ownerPhoneNum": "12345678900",
                "valid": true
            }
        ],
        "last": true,
        "totalElements": 1,
        "totalPages": 1,
        "size": 20,
        "number": 0,
        "sort": null,
        "first": true,
        "numberOfElements": 1
    }
}
```

### 4.4.11 查询指定的新能源车辆接口

- 功能描述：`查询指定的新能源车辆`

- 调用场景：`web端查询新能源车详细信息`

- 请求地址：`localhost:8080/order/vehicles/newEnergy/{id}?access_token`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/vehicles/newEnergy/31?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 返回示例：
```json
{
    "status": "SUCCESS",
    "data": {
        "id": 31,
        "carPlate": "皖A00000",
        "ownerPhoneNum": "01234567899",
        "valid": true,
        "ownerCardId": "123456789987654321",
        "engineNum": "000",
        "vin": "000",
        "registerTime": 1513159200000,
        "validDate": 1544716800000,
        "remark": "新能源车",
        "lastModifiedDate": 1513167401754
    }
}
```

### 4.4.12 条件查询新能源车的接口

- 功能描述：`根据车牌、归属人手机号、状态查询新能源车`

- 调用场景：`web端根据车牌、归属人手机号、状态查询新能源车`

- 请求地址：`localhost:8080/order/vehicles/newEnergy/query?carPlate&valid&ownerPhoneNum&access_token`
           `carPlate&valid&ownerPhoneNum是非必须的可以缺省`
- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/vehicles/newEnergy/query?carPlate=皖A12345&valid=true&ownerPhoneNum=12345678900&access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 返回示例：
```json
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 30,
                "carPlate": "皖A12345",
                "ownerPhoneNum": "12345678900",
                "valid": true,
                "ownerCardId": null,
                "engineNum": null,
                "vin": null,
                "registerTime": null,
                "validDate": null,
                "remark": null,
                "lastModifiedDate": 1513167387311
            }
        ],
        "last": true,
        "totalElements": 1,
        "totalPages": 1,
        "size": 20,
        "number": 0,
        "sort": null,
        "first": true,
        "numberOfElements": 1
    }
}
```

## 4.5 APP端获取车辆信息接口（AppVehicleController）

### 4.5.1 getArrearsParkingOrder接口
- 功能描述：分页获取车辆的欠费订单

- 请求地址：`http://domain/order/app/vehicles/{carPlate}/arrears`

- 请求动作: `GET`

- 请求示例：`http://localhost:8080/order/app/vehicles/%e7%9a%96A12345/arrears?access_token&page&size&sort`
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
                "parkingPeriod": 74,
                "arrearsFee": 0
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

- 请求示例：`http://localhost:8080/order/app/vehicles/%e7%9a%96A12345/parkingRecords?access_token&page&size&page`

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

- 请求示例：`http://localhost:8080/order/app/vehicles/%e7%9a%96A12345/paymentRecords?access_token&page&size&sort`

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
                "period": 8770,
                "appPayTypes": [
                    {
                        "fee": 222,
                        "payType": 4,
                        "payTime": "2017-08-03 17:16:14"
                    }
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

### 4.5.4 obtainArrearsStats接口

- 功能描述：获取欠费订单总笔数与总金额的统计接口

- 请求地址：`http://domain/order/app/vehicles/obtainArrearsStats`

- 请求动作: `GET`

- 请求示例：`http://domain/order/app/vehicles/obtainArrearsStats?access_token=7d3e6db0-65d7-43ea-9b9f-59eb83744345`

- 返回示例：
```
{
    "status": "SUCCESS",
    "data": {
        "num": 16,
        "sum": 30606
    }
}

```

### 4.5.5 getArrearsParkingOrderWithOutPage接口

- 功能描述：获取车辆的欠费订单列表
- 请求地址：`http://domain/order/app/vehicles/{carPlate}/arrearsWithOutPage`
- 请求动作: `GET`
- 请求示例：`http://localhost:8080/order/app/vehicles/%e7%9a%96A12345/arrears?access_token`
  - 注意事项： 车牌中的汉字须先进行url编码后方可放入url中作参数传递
- 返回示例：

```
{
    "status": "SUCCESS",
    "data": [
        {
            "orderId": 10000202,
            "roadSectionName": "潜山路-长江西路",
            "parkingAreaName": "植保路",
            "category": "路边停车",
            "createdDate": "2017-10-26 15:33:46",
            "completeDate": "2017-10-26 15:13:14",
            "parkingPeriod": -20,
            "arrearsFee": 1000
        }
    ]
}
```



## 4.6 APP端访问地图信息接口（AppMapController）

### 4.6.1 obtainUsedParkingCountGroupByRoadSection接口

- 功能描述：分组统计各个路段已使用的泊位数

- 请求地址：`http://domain/order/app/map/usedParkingCountGroupByRoadSection`

- 请求动作：`GET`

- 请求示例：`http://192.168.1.18:8080/order/app/map/usedParkingCountGroupByRoadSection?access_token`

- 返回示例：
```$xslt
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1021,
            "usedParkingNum": 31
        }
    ]
}
```


### 4.6.1 obtainUsedParkingCountByRoadSection接口

- 功能描述：根据路段统计路段已使用的泊位数

- 请求地址：`http://domain/order/app/map/usedParkingCountByRoadSection`

- 请求动作：`GET`

- 请求示例：`http://192.168.1.18:8080/order/app/map/usedParkingCountByRoadSection?access_token&roadSectionId=1021`

- 返回示例：
```$xslt
{
    "status": "SUCCESS",
    "data": 31
}
```
## 4.7 支付接口

### 4.7.1 支付宝生成App支付订单信息接口

- 功能描述：支付宝生成订单信息接口
- 请求地址：`http://doman/order/alipay/generateOrderInfo`
- 请求动作：`POST`
- 请求示例：`http://192.168.1.177:8080/order/alipay/generateOrderInfo?access_token`
- 请求实体：couponId为可选参数
```json
  {
    "orderId":1,
    "fee":1,
    "couponId":"8f86bfd2-4c12-41b3-a781-d739e8982b24"
  }
```
- 返回示例：

```$xslt
{
    "status": "SUCCESS",
    "data": "alipay_sdk=alipay-sdk-java-dynamicVersionNo&app_id=2017082108309530&biz_content=%7B%22body%22%3A%22%E5%81%9C%E8%BD%A6%E8%AE%A2%E5%8D%95%22%2C%22out_trade_no%22%3A%22201709061023443698570%22%2C%22product_code%22%3A%22QUICK_MSECURITY_PAY%22%2C%22subject%22%3A%22%E5%81%9C%E8%BD%A6%E8%AE%A2%E5%8D%95%22%2C%22timeout_express%22%3A%2230m%22%2C%22total_amount%22%3A%220.01%22%7D&charset=UTF-8&format=json&method=alipay.trade.app.pay&notify_url=http%3A%2F%2Fhfcb.asuscomm.com%3A8082%2Falipay%2Fcallback%2FappDriveOutPaymentNotify&sign=f7YoDZrk54%2FVI48%2Bhd3Jt79ab9J%2BE0vg6Vd4GWV7dqDb%2FlHcvgLJr6TXc2FrxQcRO3hnhC318eKgEK2DoDjPVwJMWwTLyse1zTtam%2BYp8QBFUSV8i0%2B0Jqe%2ByVmAsOjWfODuj8qySethA4sVJCzdPBmunPnTWAVvtiMf3wnfyVGMxvgen4cUyka4rkiUTZn8qJLr7ohAEHt5dBuMyJAIAZv0ob9C%2FAsO4ZiE4nswkRNWJN246Lb8bd74BO0tY4ZwaqbIxC5JH0gyKzf15QIQjJySak1rS67uBNiHKejAUGg2Pg89hUrGq3fu6Kkj%2Fzt3lj%2Fxqvl%2Bw03P5x%2Fzl6y6ig%3D%3D&sign_type=RSA2&timestamp=2017-09-06+10%3A23%3A44&version=1.0"
}
```



### 4.7.2 支付宝生成APP欠费补缴订单信息

- 功能描述：支付宝生成APP欠费补缴订单信息

- 请求地址：`http://doman/order/alipay/generateAppArrearsPaidOrderInfo`

- 请求动作：`POST`

- 请求示例：`http://192.168.1.177:8080/order/alipay/generateAppArrearsPaidOrderInfo?access_token`

- 请求实体

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

- 返回示例：

```$xslt
{
    "status": "SUCCESS",
    "data": "alipay_sdk=alipay-sdk-java-dynamicVersionNo&app_id=2017082108309530&biz_content=%7B%22body%22%3A%22%E5%81%9C%E8%BD%A6%E8%AE%A2%E5%8D%95%22%2C%22out_trade_no%22%3A%22201709061023443698570%22%2C%22product_code%22%3A%22QUICK_MSECURITY_PAY%22%2C%22subject%22%3A%22%E5%81%9C%E8%BD%A6%E8%AE%A2%E5%8D%95%22%2C%22timeout_express%22%3A%2230m%22%2C%22total_amount%22%3A%220.01%22%7D&charset=UTF-8&format=json&method=alipay.trade.app.pay&notify_url=http%3A%2F%2Fhfcb.asuscomm.com%3A8082%2Falipay%2Fcallback%2FappDriveOutPaymentNotify&sign=f7YoDZrk54%2FVI48%2Bhd3Jt79ab9J%2BE0vg6Vd4GWV7dqDb%2FlHcvgLJr6TXc2FrxQcRO3hnhC318eKgEK2DoDjPVwJMWwTLyse1zTtam%2BYp8QBFUSV8i0%2B0Jqe%2ByVmAsOjWfODuj8qySethA4sVJCzdPBmunPnTWAVvtiMf3wnfyVGMxvgen4cUyka4rkiUTZn8qJLr7ohAEHt5dBuMyJAIAZv0ob9C%2FAsO4ZiE4nswkRNWJN246Lb8bd74BO0tY4ZwaqbIxC5JH0gyKzf15QIQjJySak1rS67uBNiHKejAUGg2Pg89hUrGq3fu6Kkj%2Fzt3lj%2Fxqvl%2Bw03P5x%2Fzl6y6ig%3D%3D&sign_type=RSA2&timestamp=2017-09-06+10%3A23%3A44&version=1.0"
}
```

### 4.7.3 支付宝生成pos二维码支付信息

- 功能描述：支付宝生成pos二维码支付信息

- 请求地址：`http://doman/order/alipay/generateQRCodePayInfo`

- 请求动作：`POST`

- 请求示例：`http://192.168.1.177:8080/order/alipay/generateQRCodePayInfo?access_token`

- 请求实体

  ```
  {
          "orderId": 10000272,
          "fee":4,
          "employeeId": 1000,
          "posSn": "1889773"
      }
  ```

- 返回示例：

```$xslt
{
    "status": "SUCCESS",
    "data": "https://qr.alipay.com/bax08690lppetlzj4iof00c2"
}
```

### 4.7.4 支付宝生成POS欠费补缴二维码支付信息

- 功能描述：支付宝生成pos二维码支付信息

- 请求地址：`http://doman/order/alipay/generatePosArrearsPaidOrderInfo`

- 请求动作：`POST`

- 请求示例：`http://192.168.1.177:8080/order/alipay/generatePosArrearsPaidOrderInfo?access_token`

- 请求实体:

  ```json
  [
        {
          "orderId": 10000272,
          "payType":4,
          "payTime": "2017-08-13 19:21:21",
          "arrearsFee": 200,
          "tollStaffId": 1001,
          "tollStaffName": "张三",
          "tollStaffPhoneNum": "15523339872",
          "district": "蜀山区",
          "posSn": "1323232"
      },
      {
          "orderId": 10000281,
          "payType":4,
          "payTime": "2017-08-13 15:13:14",
          "arrearsFee": 199,
          "tollStaffId": 1001,
          "tollStaffName": "张三",
          "tollStaffPhoneNum": "15523339872",
          "district": "蜀山区",
          "posSn": "1323232"
      }
    ]
  ```

- 返回示例：

  ```
  {
      "status": "SUCCESS",
      "data": "https://qr.alipay.com/bax08690lppetlzj4iof00c2"
  }
  ```

### 4.7.5 微信生成App支付订单信息接口

- 功能描述：微信生成订单信息接口
- 请求地址：`http://doman/order/weChat/generateOrderInfo`
- 请求动作：`POST`
- 请求示例：`http://192.168.1.177:8080/order/weChat/generateOrderInfo?access_token`
- 请求实体：couponId为可选参数
```json
  {
    "orderId":1,
    "fee":1,
    "ip":"192.168.1.177",
    "couponId":"8f86bfd2-4c12-41b3-a781-d739e8982b24"
  }
```
- 返回示例：

```$xslt
{
    "status": "SUCCESS",
    "data": {
        "appId": "wxd5a553c228118fca",
        "partnerId": "1489500492",
        "prepayId": "wx201710091535436967022dde0414189076",
        "pack": "Sign=WXPay",
        "nonceStr": "9f5e808f26784a0fb6902fe389ec775d",
        "timestamp": "20171009153542",
        "sign": "F234F0AE95EC7ABC4314F5EB5400E7F4",
        "codeUrl": null
    }
}
```



### 4.7.6 微信生成APP欠费补缴订单信息

- 功能描述：微信生成APP欠费补缴订单信息

- 请求地址：`http://doman/order/weChat/generateAppArrearsPaidOrderInfo`

- 请求动作：`POST`

- 请求示例：`http://192.168.1.177:8080/order/weChat/generateAppArrearsPaidOrderInfo?access_token&ip`

- 请求实体

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

- 返回示例：

```$xslt
{
    "status": "SUCCESS",
    "data": {
        "appId": "wxd5a553c228118fca",
        "partnerId": "1489500492",
        "prepayId": "wx20171009154139020e8d05ef0005134656",
        "pack": "Sign=WXPay",
        "nonceStr": "ac70bc74307148bd885b340d8aa145e6",
        "timestamp": "20171009154138",
        "sign": "CB46E41C14E748A3323EAF2130C1AC92",
        "codeUrl": null
    }
}
```

### 4.7.7 微信生成pos二维码支付信息

- 功能描述：微信生成pos二维码支付信息

- 请求地址：`http://doman/order/weChat/generateQRCodePayInfo`

- 请求动作：`POST`

- 请求示例：`http://192.168.1.177:8080/order/weChat/generateQRCodePayInfo?access_token`

- 请求实体

  ```
  {
          "orderId": 10000272,
          "fee":4,
          "employeeId": 1000,
          "posSn": "1889773",
          "ip": "192.168.1.177"
      }
  ```

- 返回示例：

```$xslt
{
    "status": "SUCCESS",
    "data": "weixin://wxpay/bizpayurl?pr=nIPVy3F"
}
```

### 4.7.8 微信生成POS欠费补缴二维码支付信息

- 功能描述：微信生成pos二维码支付信息

- 请求地址：`http://doman/order/weChat/generatePosArrearsPaidOrderInfo`

- 请求动作：`POST`

- 请求示例：`http://192.168.1.177:8080/order/weChat/generatePosArrearsPaidOrderInfo?access_token`

- 请求实体:

  ```json
  [
        {
          "orderId": 10000272,
          "payType":4,
          "payTime": "2017-08-13 19:21:21",
          "arrearsFee": 200,
          "tollStaffId": 1001,
          "tollStaffName": "张三",
          "tollStaffPhoneNum": "15523339872",
          "district": "蜀山区",
          "posSn": "1323232"
      },
      {
          "orderId": 10000281,
          "payType":4,
          "payTime": "2017-08-13 15:13:14",
          "arrearsFee": 199,
          "tollStaffId": 1001,
          "tollStaffName": "张三",
          "tollStaffPhoneNum": "15523339872",
          "district": "蜀山区",
          "posSn": "1323232"
      }
    ]
  ```

- 返回示例：

  ```
  {
      "status": "SUCCESS",
      "data": "weixin://wxpay/bizpayurl?pr=9lPgO3H"
  }
  ```

### 4.7.9 小程序生成App支付订单信息接口

- 功能描述：小程序生成订单信息接口
- 请求地址：`http://domain/order/weChat/generateMiniAppPaidOrderInfo`
- 请求动作：`POST`
- 参数位置：`Request Parameter`
- 请求参数：
    - code: code
- 请求示例：`http://192.168.1.177:8080/order/weChat/generateMiniAppPaidOrderInfo?access_token=&code=`
- 请求实体：couponId为可选参数
```json
  {
    "orderId":1,
    "fee":1,
    "ip":"192.168.1.177",
    "couponId":"8f86bfd2-4c12-41b3-a781-d739e8982b24"
  }
```
- 返回示例：

```$xslt
{
    "status": "SUCCESS",
    "data": {
        "appId": "wxd5a553c228118fca",
        "partnerId": "1489500492",
        "prepayId": "wx20171103083244b44a6be1650109385307",
        "pack": "Sign=WXPay",
        "nonceStr": "a2992f9f7429465490d74819dac268b7",
        "timestamp": "1509669162",
        "sign": "DDC4A71221459ED45A11AC0FABDCC9F2"
    }
}
```



### 4.7.10 小程序生成APP欠费补缴订单信息

- 功能描述：小程序生成APP欠费补缴订单信息

- 请求地址：`http://domain/order/weChat/generateMiniAppArrearsPaidOrderInfo`

- 请求动作：`POST`
- 参数位置：`Request Parameter`
- 请求参数：
    - code: code

- 请求示例：`http://192.168.1.177:8080/order/weChat/generateMiniAppArrearsPaidOrderInfo?access_token&ip=&code=`

- 请求实体

  ```
    [
        {
            "orderId":10000272,
            "arrearsFee":4,
            "payType":8,
            "payTime":"2017-10-10 12:23:23",
            "tollStaffId":12,
            "tollStaffName":"王五",
            "tollStaffPhoneNum":"15009892222",
            "district":"蜀山区",
            "posSn":"863127038052954"
        },
        {
            "orderId":10000281,
            "arrearsFee":4,
            "payType":8,
            "payTime":"2017-10-10 12:23:23",
            "tollStaffId":12,
            "tollStaffName":"王五",
            "tollStaffPhoneNum":"15009892222",
            "district":"蜀山区",
            "posSn":"863127038052954"
        }
    ]
  ```

- 返回示例：

```$xslt
{
    "status": "SUCCESS",
    "data": {
        "appId": "wxd5a553c228118fca",
        "partnerId": "1489500492",
        "prepayId": "wx201711030824212ec960f5fe0013390617",
        "pack": "Sign=WXPay",
        "nonceStr": "4427d68545ab4c639a05e8b664d7fc7a",
        "timestamp": "1509668659",
        "sign": "E6B37A304C97049A76DA821FF384F908"
    }
}
```
  ​

## 4.8 订单数量访问接口(OrderQuantityController)

### 4.8.1 getLast30DaysOrderQuantities接口

- 功能描述：统计近30天的订单量

- 请求地址：`http://domain/order/orderQuantities/getLast30DaysOrderQuantities`

- 请求动作：`GET`

- 请求示例：`http://localhost:8080/order/orderQuantities/getLast30DaysOrderQuantities?access_token=4d04bb9b-6941-4db0-a52f-a74e4f3b8219`


- 返回示例：
```$xslt
{
    "status": "SUCCESS",
    "data": [
        {
            "date": "2017-08-30 00:00:00",
            "num": 2
        }
    ]
}
```

## 4.9 订单变更接口

### 4.9.1 消除欠费订单

- 功能描述：消除欠费的订单

- 请求地址：`http://domain/order/orders/clearArrears`

- 请求动作：`PUT`

- 请求示例：`http://domain/order/orders/clearArrears?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`


- 请求示例：
```$xslt
{
	"ids":[
		10000099,10000007
		],
		"reason":"收费失误"
}
```

### 4.9.2 变更订单金额

- 功能描述：变更订单金额

- 请求地址：`http://domain/order/orders/{id}/modifyFee`

- 请求动作：`PUT`

- 请求示例：`http://localhost:8080/order/orders/10000018/modifyFee?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

- 请求示例：

```$xslt
{
	"fee":300,
	"reason":"未找到收费员"
}
```

### 4.9.3 查询变更订单信息

- 功能描述：查询变更订单记录信息（按变更时间倒序排列）

- 请求地址：`http://domain/order/orders/{id}/orderLogs`

- 请求动作：`GET`

- 请求示例：`localhost:8080/order/orders/10000018/modifiedRecords?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`


- 返回示例：
```$xslt{
            "status": "SUCCESS",
            "data": [
                {
                    "orderId": 10000018,
                    "operatorUsername": "admin",
                    "originArrearsFee": 1000,
                    "currentFee": 300,
                    "remark": "未找到收费员",
                    "type": 2,
                    "description": "修改应交金额",
                    "time": "2017-12-15 18:09:16"
                }
            ]
        }
```
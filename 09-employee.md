## 9.1 扎帐
### 9.1.1 获取扎帐金额
- 功能描述: 获取扎帐金额

- 请求地址: `http://domain/employee/accounting/calAccount?access_token=token`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/employee/accounting/calAccount?access_token=85221cc0-9837-45b9-bb72-29e7af104de1`

- 返回示例

  ```
  {
      "status": "SUCCESS",
      "data": {
          "totalFee": 46607,
          "details": [
              {
                  "date": "2017-07-13",
                  "fee": 9293
              },
              {
                  "date": "2017-08-03",
                  "fee": 302
              },
              {
                  "date": "2017-08-13",
                  "fee": 101
              },
              {
                  "date": "2017-08-15",
                  "fee": 4000
              },
              {
                  "date": "2017-08-16",
                  "fee": 8000
              },
              {
                  "date": "2017-08-17",
                  "fee": 16000
              },
              {
                  "date": "2017-08-18",
                  "fee": 8000
              },
              {
                  "date": "2017-08-21",
                  "fee": 812
              }
          ]
      }
  }
  ```
### 9.1.2 生成扎帐支付宝支付二维码信息

- 功能描述: 生成扎帐支付二维码信息


- 请求地址: `http://domain/employee/accounting/generateAlipayQRCode`
- 请求动作: `POST`
- 请求示例: `http://domain/employee/accounting/generateAlipayQRCode?access_token=token&posSn=111`
- 返回示例
```$xslt
{
    "status": "SUCCESS",
    "data": "http://xx"
}
```

### 9.1.3 生成扎帐微信支付二维码信息

- 功能描述: 生成扎帐支付二维码信息


- 请求地址: `http://domain/employee/accounting/generateWeChatQRCode?access_token=token`
- 请求动作: `POST`
- 请求示例: `http://domain/employee/accounting/generateWeChatQRCode?access_token=token&posSn=111&ip=192.168.1.177`
- 返回示例
```$xslt
{
    "status": "SUCCESS",
    "data": "weixin://wxpay/bizpayurl?pr=d1Rn0zD"
}
```

### 9.1.4 扎帐流水

- 功能描述: 查询扎帐流水
- 请求地址: `http://domain/employee/accounting`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/employee/accounting?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&name=姚望&phoneNum=18651893733&status=1&accountTime=2017-10-31&username=yaow&sort=createdDate,Desc`
- 请求参数:
    - `name`: 员工姓名
    - `username`: 员工工号
    - `phoneNum`: 手机号
    - `status`: 扎帐状态,1成功,2失败
    - `accountTime`: 扎帐日期，格式为yyyy-MM-dd
- 返回示例

```json
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1002,
                "name": "姚望",
                "username": "yaow",
                "phoneNum": "18651893733",
                "tradeId": "201710311920188268244",
                "fee": 1,
                "date": "2017-10-31 19:20:19",
                "payType": "支付宝",
                "posSn": "111",
                "status": "成功"
            },
            ...
        ],
        "last": true,
        "totalElements": 4,
        "totalPages": 1,
        "size": 20,
        "number": 0,
        "first": true,
        "sort": null,
        "numberOfElements": 4
    }
}
```

### 9.1.5 扎帐流水导出

- 功能描述: 扎帐流水导出为excel
- 请求地址: `http://domain/employee/accounting/exportExcel`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/employee/accounting/exportExcel?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&name=姚望&phoneNum=18651893733&status=1&accountTime=2017-10-31&username=yaow`
- 请求参数:
    - `name`: 员工姓名
    - `username`: 员工工号
    - `phoneNum`: 手机号
    - `status`: 扎帐状态,1成功,2失败
    - `accountTime`: 扎帐日期，格式为yyyy-MM-dd
    

## 9.2 公司报表

### 9.2.1 查询公司对账报表

- 功能描述: 查询公司对账报表
- 请求地址: `http://domain/employee/companyAccountReports/query`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/employee/companyAccountReports/query?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&date=`
- 返回参数:
```
{
    "alipay":10,
    "weChat":10,
    "date":2018-1-1 00:00:00   
}
```

### 9.2.2 导出公司对账报表

- 功能描述: 导出公司对账报表
- 请求地址: `http://domain/employee/companyAccountReports/export`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/employee/companyAccountReports/export?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&date=`


## 9.3 公司报表2

### 9.3.1 查询公司对账报表

- 功能描述: 查询公司对账报表
- 请求地址: `http://domain/employee/companyOperatingReports/query`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/employee/companyOperatingReport/query?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&date=`
- 返回参数:
```
{
    "date":,
    "parking":10,//当天收费总额
    "arrearsPaid":10,//当天收欠费总额
    "monthBill":0,//当天购买月票总额
    "received":10,//到账金额
    "notAccounted":10，//未扎帐
    "coupon":10//优惠券金额
}
```

### 9.3.2 导出公司对账报表

- 功能描述: 导出公司对账报表
- 请求地址: `http://domain/employee/companyOperatingReport/export`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/employee/companyOperatingReport/export?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&date=`




## 9.4 员工报表

### 9.4.1 员工报表

- 功能描述: 查询员工对账报表
- 请求地址: `http://domain/employee/employeeReports/query`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/employee/employeeReports/query?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&parkingAreaName=&roadSectionName=&employeeName=&username=&district=&startDate&endDate=`
- 返回参数:
```
{
    "date":,
    "name":,
    "username":,
    "district":,
    "roadSectionName":,
    "parkingAreaName":,
    "postName":,
    "cash":0,// 当日现金收费总金额
    "alipay":0,// 当日支付宝收费总金额
    "weChat"0,// 当日微信收费总金额
    "cashArrears":0,// 当日现金补缴总金额
    "alipayArrears":0,// 当日支付宝补缴总金额
    "weChatArrears":0,// 当日微信补缴总金额
    "todayAccounted":0,
    "notAccounted":0,// 未扎帐总金额
    "replenishAccount":0,
    "arrears":0,// 打欠费订单的金额
    "total":0// 入账总计
}
```

### 9.3.2 导出员工对账报表

- 功能描述: 导出公司对账报表
- 请求地址: `http://domain/employee/employeeReport/export`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/employee/employeeReport/export?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&&parkingAreaName=&roadSectionName=&employeeName=&username=&district=&startDate&endDate=`



## 常量

### 发票抬头常量

- `type` : 1为个人，2为公司

### 发票类型常量

- `DEFAULT_TYPE` :停车费

### 发票状态常量

- `InvoiceStatus`: WAIT_INVOICE:1, INVOICED:2, OVERDUE:3, FAILURE: 4

### 发票常量
 
  - `BLUE_INVOICE`:"0"    红票
     `RED_INVOICE` : "1" 蓝票
     `PRODUCT_CODE` : "3040502020200000000" 商品编码
     `COMMON_TAX` : "0" 普通征税方式
     `COMMON_INVOICE_LINE` : "0"; 正常发票行
     `FIRST_LINE` : "1"  第一行
     `PARKING_ORDER_FEE_ITEM` : "停车费"
     `TAX_RATE` : 0.05  税率
     `APP_ID` : "dzfp"
     `DRAW_INVOICE` : "REQUEST_E_FAPIAO_KJ"  开发票接口名称

## 14.1 电子发票抬头信息访问接口

### 14.1.1 新增电子发票抬头

- 功能描述:  新增电子发票抬头
- 请求地址: `http://domain/customer/titles`
- 请求动作: `POST`
- 请求示例: `http://domain/customer/titles?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
- 请求示例
```
{
	"title":"抬头名称",
	"buyerId":"税号",
	"isDefault":false//默认状态，
	"type":1
}
```

- 返回示例
```
{
    "status": "SUCCESS",
    "data": "添加发票抬头成功"
}
```


### 14.1.2 查询发票抬头信息

- 功能描述:  查询发票抬头信息
- 请求地址: `http://domain/customer/titles`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/titles?access_token=be7c3399-de89-481c-acba-d5987050c81a`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 149,
            "title": "合肥城市泊车投资管理有限公司",
            "buyerId": "777777",
            "isDefault": false,
            "phoneNum": "15555417041",
            "type": 2
        },
        {
            "id": 152,
            "title": "保安集团",
            "buyerId": "111111",
            "isDefault": false,
            "phoneNum": "15555417041",
            "type": 2
        }
    ]
}
```

### 14.1.3 更新发票抬头信息

- 功能描述:  查询发票抬头信息
- 请求地址: `http://domain/customer/titles/{id}`
- 请求动作: `PUT`
- 请求示例: `http://domain/customer/titles/1?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
```
{
	"title":"抬头名称",
	"buyerId":"税号",
	"isDefault":false,
	"type":1
}
```
- 返回示例：
```
{
    "status": "SUCCESS",
    "data": "更新发票抬头成功"
}
```

### 14.1.4 查询默认发票抬头信息

- 功能描述:  查询默认发票抬头信息
- 请求地址: `http://domain/customer/titles/default`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/titles/default?&access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回示例：
```
{
    "status": "SUCCESS",
    "data": {
        "id": 22,
        "title": "公司",
        "buyerId": "456",
        "isDefault": true,
        "phoneNum": "15555417041",
        "type":2
    }
}
```

### 14.1.5 删除发票抬头信息

- 功能描述:  删除发票抬头信息
- 请求地址: `http://domain/customer/titles/{id}`
- 请求动作: `DELETE`
- 请求示例: `http://domain/customer/titles/1?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回示例：
```
{
    "status": "SUCCESS"
}
```


## 14.2 发票订单信息访问接口

### 14.2.1 客户查询指定区域下的发票订单

- 功能描述: 查询指定区域下的发票订单信息

- 请求地址: `localhost:8080/customer/invoiceOrders/list?access_token&districtId`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/customer/invoiceOrders/list?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&districtId=1002&carPlates=皖A12345,皖A00000`

- 返回示例
```{
       "status": "SUCCESS",
       "data": [
           {
               "date": "2017-12",
               "invoiceMonthBillOrderDtos": [
                   {
                       "id": 1035,
                       "completeDate": "2017-12-22 15:42:37 星期五",
                       "isMonthBill": false,
                       "carPlate": "皖A12346",
                       "parkingAreaName": "888",
                       "roadSectionName": "望江西路",
                       "parkingPeriod": null,
                       "fee": 10000,
                       "startMonth": "2018-01-01 00:00:00",
                       "endMonth": "2018-04-30 23:59:59"
                   },
                   {
                       "id": 1036,
                       "completeDate": "2017-12-22 15:43:23 星期五",
                       "isMonthBill": false,
                       "carPlate": "皖A12346",
                       "parkingAreaName": "888",
                       "roadSectionName": "望江西路",
                       "parkingPeriod": null,
                       "fee": 10000,
                       "startMonth": "2018-01-01 00:00:00",
                       "endMonth": "2018-04-30 23:59:59"
                   },
                   {
                       "id": 1037,
                       "completeDate": "2017-12-22 15:49:28 星期五",
                       "isMonthBill": false,
                       "carPlate": "皖A12346",
                       "parkingAreaName": "888",
                       "roadSectionName": "望江西路",
                       "parkingPeriod": null,
                       "fee": 10000,
                       "startMonth": "2018-01-01 00:00:00",
                       "endMonth": "2018-04-30 23:59:59"
                   },
                   {
                       "id": 1038,
                       "completeDate": "2017-12-22 15:54:28 星期五",
                       "isMonthBill": false,
                       "carPlate": "皖A12346",
                       "parkingAreaName": "888",
                       "roadSectionName": "望江西路",
                       "parkingPeriod": null,
                       "fee": 10000,
                       "startMonth": "2018-01-01 00:00:00",
                       "endMonth": "2018-04-30 23:59:59"
                   }
               ]
           }
       ]
   }
```
### 14.2.2 客户查询指定区域下的未开具发票的月票

- 功能描述: 查询指定区域下的未开具发票的月票

- 请求地址: `http://domain:8080/customer/invoiceOrders/list/monthBill`

- 请求动作: `GET`

- 请求示例: `http://domain:8080/customer/invoiceOrders/list/monthBill?access_token=cd6a60af-9ecf-489e-95b7-8a5fc87684b0&districtId=1&carPlates=皖A12346`

- 返回示例
```

{
    "status": "SUCCESS",
    "data": [
        {
            "date": "2017-12",
            "invoiceMonthBillOrderDtos": [
                {
                    "id": 1035,
                    "completeDate": "2017-12-22 15:42:37 星期五",
                    "isMonthBill": false,
                    "carPlate": "皖A12346",
                    "parkingAreaName": "888",
                    "roadSectionName": "望江西路",
                    "parkingPeriod": null,
                    "fee": 10000,
                    "startMonth": "2018-01-01 00:00:00",
                    "endMonth": "2018-04-30 23:59:59"
                },
                {
                    "id": 1036,
                    "completeDate": "2017-12-22 15:43:23 星期五",
                    "isMonthBill": false,
                    "carPlate": "皖A12346",
                    "parkingAreaName": "888",
                    "roadSectionName": "望江西路",
                    "parkingPeriod": null,
                    "fee": 10000,
                    "startMonth": "2018-01-01 00:00:00",
                    "endMonth": "2018-04-30 23:59:59"
                },
                {
                    "id": 1037,
                    "completeDate": "2017-12-22 15:49:28 星期五",
                    "isMonthBill": false,
                    "carPlate": "皖A12346",
                    "parkingAreaName": "888",
                    "roadSectionName": "望江西路",
                    "parkingPeriod": null,
                    "fee": 10000,
                    "startMonth": "2018-01-01 00:00:00",
                    "endMonth": "2018-04-30 23:59:59"
                },
                {
                    "id": 1038,
                    "completeDate": "2017-12-22 15:54:28 星期五",
                    "isMonthBill": false,
                    "carPlate": "皖A12346",
                    "parkingAreaName": "888",
                    "roadSectionName": "望江西路",
                    "parkingPeriod": null,
                    "fee": 10000,
                    "startMonth": "2018-01-01 00:00:00",
                    "endMonth": "2018-04-30 23:59:59"
                }
            ]
        }
    ]
}
```




## 14.3 发票信息访问接口

### 14.3.1 获取行政区接口

- 功能描述:  获取行政区列表
- 请求地址: `http://domain/customer/invoices/districts`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/invoices/districts?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1001,
            "name": "庐阳区"
        },
        {
            "id": 1002,
            "name": "蜀山区"
        },
        {
            "id": 1003,
            "name": "包河区"
        },
        {
            "id": 1004,
            "name": "瑶海区"
        },
        {
            "id": 1005,
            "name": "庐江县"
        },
        {
            "id": 1006,
            "name": "肥东县"
        },
        {
            "id": 1007,
            "name": "肥西县"
        }
    ]
}
```


### 14.3.2 停车订单开发票接口

- 功能描述:  停车订单开发票
- 请求地址: `http://domain/customer/invoices`
- 请求动作: `POST`
- 请求示例: `http://domain/customer/invoices?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 请求数据示例  
```
{
    "districtId":1001,
    "ids":[],
    "title":"李剑",
    "buyerId":"12344",
    "mail":"479159321@qq.com"，
    "type":"1"
}

```

- 返回数据示例  
```
{
    "status": "SUCCESS"
}

```


### 14.3.3 开票流水接口

- 功能描述:  获取个人所有的开票记录
- 请求地址: `http://domain/customer/invoices/list`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/customer/invoices/list?access_token=69f4f17d-1e14-4c6b-a711-c5b02ebed275&page=0&size=4&sort=createdDate,DESC`


- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 864,
                "status": 4,
                "type": "停车费",
                "price": "40.0",
                "createdTime": "2017-12-20 16:19:05"
            },
            {
                "id": 863,
                "status": 4,
                "type": "停车费",
                "price": "40.0",
                "createdTime": "2017-12-20 16:17:33"
            }
        ],
        "last": false,
        "totalElements": 69,
        "totalPages": 35,
        "number": 0,
        "size": 2,
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
        "first": true,
        "numberOfElements": 2
    }
}

```

### 14.3.4 电子发票详情接口

- 功能描述:  根据id获取电子发票详情
- 请求地址: `http://domain/customer/invoices/{id}`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/invoices/64?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`


- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": {
        "id": 64,
        "title": "李剑",
        "type": "停车费",
        "price": "1.0",
        "email": "479159321@qq.com",
        "pdfUrl": "http://111.202.226.69:9026/zxkp/pdf?c=6bf213a81c1824940ca6",
        "number":4,
        "goodsType"：1     ////发票类型   1：订单停车费  2：月票停车费
    }
}

```

### 14.3.5 重发邮件接口

- 功能描述:  重新发送邮件
- 请求地址: `http://domain/customer/invoices/resendEmail`
- 请求动作: `PUT`
- 请求示例: `http://domain/customer/invoices/resendEmail?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&id=156&email=1184750950@qq.com`


- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": "邮件发送成功"
}

```


### 14.3.6 月票开发票接口

- 功能描述:  创建月票的电子发票
- 请求地址: `http://domain/customer/invoices/monthBill`
- 请求动作: `POST`
- 请求示例: `http://domain/customer/invoices/monthBill?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 请求数据示例  
```
{
    "districtId": 1001,
    "ids":[
        64,32
    ],
    "title":"abc",
    "buyerId":"123",
    "mail":"123@qq.com",
    "type":"1"
}

```


- 返回数据示例  
```
{
    "status": "SUCCESS"
}

```


### 14.3.7 获取发票订单接口

- 功能描述:  客户查询指定电子发票下的订单
- 请求地址: `http://domain/customer/invoices/{id}/orders`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/invoices/64/orders?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`


- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": [
        {
            "completeDate": "2017-12-06 22:13:14 星期三",
            "isMonthBill": false,
            "roadSectionName": "潜山路-长江西路",
            "parkingPeriod": -616,
            "fee": 4000
        }
    ]
}

```

### 14.3.8 纸质发票接口

- 功能描述:  客户开具纸质发票
- 请求地址: `http://domain/customer/invoices/paperInvoice`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/customer//web/invoices/monthBill/paper?access_token=9e02c0ba-3042-4e41-aed4-80c0cccbafab`
- 请求示例  
```
{
	  "type":1,
      "invoiceNum":"001",
      "invoiceCode":"123",
      "invoiceTitle":"合肥城泊",
      "buyerId":"123456789",
      "taxRate":"0.05",
      "taxAmount":"100",
      "afterTaxIncome":"2000",
      "monthBillId":1011,
      "districtId":1001                     
}

```


### 14.3.9 停车订单便捷开发票接口

- 功能描述:  停车订单便捷开发票接口
- 请求地址: `http://domain/customer/invoices/convenience`
- 请求动作: `POST`
- 请求示例: `http://domain/customer/invoices/convenience?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 请求数据示例  
```
{
    "districtId": 1001,
    "ids":[
        "444144404440444044404440444344414447"
    ],
    "title":"abc",
    "mail":"123@qq.com",
    "type":"1"
}

```


- 返回数据示例  
```
开票成功
{
    "status": "SUCCESS"
}
开票失败
{
    "status": "FAILURE"
}
```

### 14.3.10 获取发票下月票信息接口

- 功能描述:  客户查询指定电子发票下的月票
- 请求地址: `http://domain/customer/invoices/{id}/monthBills`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/invoices/1021/monthBills?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`


- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1028,
            "completeDate": "2017-12-20 08:53:59 星期三",
            "carPlate": "皖A99999",
            "parkingAreaName": null,
            "roadSectionName": [
                "望江西路",
                "长江西路",
                "潜山路"
            ],
            "startMonth": "2017-12-20 08:53:59",
            "endMonth": "2017-12-20 08:53:59",
            "fee": 10000
        }
    ]
}

```

### 14.3.11 获取存在可开发票的订单和月票所属行政区列表接口

- 功能描述:  获取存在可开发票的订单和月票所属行政区列表
- 请求地址: `http://domain/customer/invoices/query/districts`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/invoices/query/districts?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1001,
            "name": "庐阳区"
        }
    ]
}
```

## 14.4 Web端发票信息访问接口

### 14.4.1 Web端发票列表接口

- 功能描述:  Web端获取电子发票列表
- 请求地址: `http://localhost:8080/customer/web/invoices/query`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/customer/web/invoices/query?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&invoiceNumber=20171208091042646444&invoicePhoneNum=adm&invoiceType&status=1&invoiceStartTime&invoiceEndTime&page=0&size=20&sort`

- 请求数据示例  
```
{
    "invoiceNumber": "发票号码",
    "invoicePhoneNum":"手机号码",
    "invoiceType":0,        //发票类型 0：蓝票 1：红票
    "status":1,             //开票状态 1：待开具 2：已开具
    "invoiceStartTime":"2017-11-08 11：11：11",
    "invoiceEndTime":"2017-11-08 11：11：11",
    "issueInvoiceType":1 //1：电子发票 2：纸质发票
}

```


- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 162,  
                "invoiceCode": null,        //发票代码
                "invoiceNumber": null,      //发票号码
                "invoiceInfoType": "0",     发票类型 0蓝1红
                "invoiceInfoConsumerPhoneNum": "admin",     //消费者手机号码
                "buyerMail": "479159321@qq.com",        //邮箱
                "globalInfoRequestTime": "2017-12-08 09:11:05",     //申请时间
                "invoiceInfoSalerName": "测试",       开票公司
                "invoiceInfoPriceAndTaxAmount": "50.05",        //开票金额
                "invoiceInfoTax": "5%",     //税率
                "invoiceInfoTaxAmount": "2.38",     //税额
                "invoiceInfoPriceAmount": "47.669999999999995",     //税后收入
                "invoiceInfoTitle": "李剑",       //发票抬头
                "invoiceInfoSerialNumber": "20171208091042646444",      //发票税号
                "invoiceInfoBuyerName": "李剑",   //开票对象
                "status": 1,        发票状态1：待开2：已开
                "invoiceInfoOriginBlueInvoiceNum": "",      //原蓝票号码
                "invoiceCreatedTime": "2017-12-08 09:11:05"     //创建时间
            },
            {
                "id": 163,
                "invoiceCode": null,
                "invoiceNumber": null,
                "invoiceInfoType": "0",
                "invoiceInfoConsumerPhoneNum": "admin",
                "buyerMail": "479159321@qq.com",
                "globalInfoRequestTime": "2017-12-08 09:11:45",
                "invoiceInfoSalerName": "测试",
                "invoiceInfoPriceAndTaxAmount": "50.05",
                "invoiceInfoTax": "5%",
                "invoiceInfoTaxAmount": "2.38",
                "invoiceInfoPriceAmount": "47.669999999999995",
                "invoiceInfoTitle": "李剑",
                "invoiceInfoSerialNumber": "20171208091145685883",
                "invoiceInfoBuyerType": "个人/公司",
                "status": 1,
                "invoiceInfoOriginBlueInvoiceNum": "",
                "invoiceCreatedTime": "2017-12-08 09:11:45"
            }
        ],
        "totalElements": 13,
        "last": true,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 13
    }
}

```


### 14.4.2 Web端发票详情接口

- 功能描述:  Web端获取发票详情
- 请求地址: `http://localhost:8080/customer/web/invoices/162`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/customer/web/invoices/162?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`



- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": {
        "invoiceCode": "111001371071",
        "invoiceNumber": "70043894",
        "invoiceInfoBuyerType": "1",
        "invoiceInfoBuyerName":"公司"，
        "invoiceInfoType": "0",
        "invoiceInfoSerialNumber": "20171227103545988117",
        "invoiceInfoPriceAndTaxAmount": "1.0",
        "invoiceInfoTax": "5%",
        "invoiceInfoTaxAmount": "0.05",
        "invoiceInfoPriceAmount": "0.95",
        "customerPhoneNum": "admin",
        "buyerMail": "1184750950@qq.com",
        "globalInfoRequestTime": "2017-12-27 10:35:45",
        "invoiceInfoSalerN
        "invoiceOrders": null,
        "invoiceMonthBills": [
            {
                "customerCarPlateame": null,
                                                             "status": 2,": "皖A10101",
                "customerPhoneNum": "18505652621",
                "roadSectionIds": [
                    1040
                ],
                "startMonth": 1517484399000
                "endMonth": 1517414399000,
                "createDate": 1514017989198,
                "actualPay": 1
            }
        ],
        "invoiceCreatedTime": 1514342145989
    }
}```
### 14.4.3 web端根据订单ID查询发票信息
- 功能描述: web端根据订单ID查询发票信息

- 请求地址: `localhost:8080/customer/web/invoiceOrders/{id}/getInvoice?access_token`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/customer/web/invoiceOrders/10000009/getInvoice?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c4`

- 返回示例
```aidl
{
    "status": "SUCCESS",
    "data": {
        "invoiceInfoSalerNameAbbr": null,
        "invoiceCode": "111001371071",
        "invoiceNumber": "70040241",
        "invoiceInfoBuyerType": null,
        "invoiceInfoBuyerId": null,
        "invoiceInfoBuyerName": "李剑",
        "createdDate": null
    }
}

```







### 14.4.3 Web端发票流水导出xls文件接口

- 功能描述:  Web端导出发票流水
- 请求地址: `http://localhost:8080/customer/web/invoices/exportExcel`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/customer/web/invoices/exportExcel?invoiceStartTime=2017-12-01%2009:11:45&invoiceEndTime=2017-12-11%2009:11:45&access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431

`- 请求数据示例  
 ```
 {
     "invoiceNumber": "发票号码",
     "invoicePhoneNum":"手机号码",
     "invoiceType":0,        //发票类型 0：蓝票 1：红票
     "status":1,             //开票状态 1：待开具 2：已开具
     "invoiceStartTime":"2017-11-08 11：11：11",
     "invoiceEndTime":"2017-11-08 11：11：11",
 }
 
 ```
 
 ### 14.4.4 发票冲红接口
 
 - 功能描述:  根据id冲红蓝字发票
 - 请求地址: `http://domain/customer/web/invoices/{id}`
 - 请求动作: `DELETE`
 - 请求示例: `http://domain/customer/web/invoices/64?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
 
 
 - 返回数据示例  
 ```
 {
     "status": "SUCCESS"
 }
 
 ```
 
 ### 14.4.5 查询指定电子订单下的订单信息
 - 功能描述: 查询指定电子订单下订单信息
 
 - 请求地址: `localhost:8080/customer/invoices/{id}/orders?access_token`
 
 - 请求动作: `GET`
 
 - 请求示例: `http://localhost:8080/customer/invoices/170/orders?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`
 
 - 返回示例
 ```aidl
 {
     "status": "SUCCESS",
     "data": [
         {
             "id": 10000019,
             "completeDate": "2017-09-15 16:56:29 星期五",
             "isMonthBill": false,
             "carPlate": "皖A00000",
             "parkingAreaName": null,
             "roadSectionName": "潜山路-长江西路",
             "parkingPeriod": 94,
             "fee": 600
         },
         {
             "id": 10000003,
             "completeDate": "2017-09-14 15:13:14 星期四",
             "isMonthBill": true,
             "carPlate": "皖A66666",
             "parkingAreaName": null,
             "roadSectionName": "潜山路-长江西路",
             "parkingPeriod": 4272,
             "fee": 4000
         }
     ]
 }
 ```
 
 ### 14.4.6 web端创建月票电子发票接口
 
 - 功能描述:  创建月票的电子发票
 - 请求地址: `http://domain/customer/web/invoices/monthBill`
 - 请求动作: `POST`
 - 请求示例: `http://domain/customer/web/invoices/monthBill?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
 
 - 请求数据示例  
 ```
 {
     "districtId": ,
     "ids":[
         1000
     ],
     "title":"合肥城泊",
     "buyerId":"91340100695707415Y",
     "mail":"1184750950@qq.com",
     "type":"2"
 }
 
 ```
 
 
 - 返回数据示例  
 ```
 {
     "status": "SUCCESS"
 }
 


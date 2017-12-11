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
	"isDefault":false//默认状态
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
- 请求示例: `http://domain/customer/titles?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 16,
            "title": "个人修改",
            "buyerId": "777",
            "isDefault": false,
            "phoneNum": "15555417041"
        },
        {
            "id": 22,
            "title": "公司",
            "buyerId": "456",
            "isDefault": true,
            "phoneNum": "15555417041"
        },
        {
            "id": 118,
            "title": "抬头名称",
            "buyerId": "税号",
            "isDefault": false,
            "phoneNum": "手机号码"
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
	"isDefault":false
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
        "phoneNum": "15555417041"
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

- 功能描述:  查询指定区域下的发票订单
- 请求地址: `http://domain/customer/invoiceOrders/list`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/invoiceOrders/list?districtId=1002&access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回示例：
```
{
    "status": "SUCCESS",
    "data": [
        {
            "completeDate": "2017-09-15 15:13:14 星期五",
            "isMonthBill": false,
            "roadSectionName": "潜山路-长江西路",
            "parkingPeriod": 301,
            "fee": 4000
        },
        {
            "completeDate": "2017-09-14 15:13:14 星期四",
            "isMonthBill": false,
            "roadSectionName": "潜山路-长江西路",
            "parkingPeriod": 286,
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


## 14.3 发票信息访问接口

### 14.3.1 获取行政区列表接口

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
    "titleCmd":{
        "title":"李剑"
    },
    "buyerId":"12344",
    "mail":"479159321@qq.com"
}

```

- 返回数据示例  
```
{
    "status": "SUCCESS"
}

```


### 14.3.3 获取所有开票记录接口

- 功能描述:  获取个人所有的开票记录
- 请求地址: `http://domain/customer/invoices/list`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/customer/invoices/list?access_token=c67010ce-be53-476f-808e-84bbf5e6f7d7&page=0&size=20&sort=globalInfoRequestTime,DESC`


- 返回数据示例  
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 64,
            "status": 2,
            "type": "停车费",
            "price": "1.0",
            "createdTime": "2017-12-07 11:27:53"
        }
    ]
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
        "pdfUrl": "http://111.202.226.69:9026/zxkp/pdf?c=6bf213a81c1824940ca6"
    }
}

```

### 14.3.5 发票冲红接口

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

### 14.3.5 重发邮件接口

- 功能描述:  重新发送邮件
- 请求地址: `http://domain/customer/invoices/resendEmail`
- 请求动作: `PUT`
- 请求示例: `http://domain/customer/invoices/resendEmail?id=64&access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`


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
    "mail":"123@qq.com"
}

```


- 返回数据示例  
```
{
    "status": "SUCCESS"
}

```


### 14.3.7 客户查询指定电子发票订单接口

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
    "invoiceStartTime":"151738176318763",
    "invoiceEndTime":"151738176318763",
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
                "invoiceInfoBuyerName": "李剑",
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
        "invoiceOrders": [
            {
                "id":1      //订单编号
                "carPlate":"皖A12345"    //车牌
                "roadSectionName":"长江西路"    //缴费路段
                "completeDate": "2017-08-11 11：11：11"   //订单完成时间
                "arrearsPaidDate":"2017-08-11 11：11：11"   //欠费补缴时间
                "fee":2.00      //缴费金额
            }
        ]
    }
}

```
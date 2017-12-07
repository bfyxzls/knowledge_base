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
- 请求示例: `http://domain/customer/titles/default?phoneNum=&access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

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

- 功能描述:  删除发票抬头信息
- 请求地址: `http://domain/customer/invoiceOrders/list`
- 请求动作: `DELETE`
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


## 14.3 Invoice Controller接口

### 14.3.1 districts接口

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


### 14.3.2 createParkingInvoice接口

- 功能描述:  停车订单开发票
- 请求地址: `http://domain/customer/invoices`
- 请求动作: `POST`
- 请求示例: `http://domain/customer/invoices?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 请求数据示例  
```
{
    "districtId":1001,
    "orderIds":[],
    "titleCmd":{
        "title":"李剑"
    },
    "mail":"479159321@qq.com"
}

```

- 返回数据示例  
```
{
    "status": "SUCCESS"
}

```


### 14.3.3 list接口

- 功能描述:  获取个人所有的开票记录
- 请求地址: `http://domain/customer/invoices/list`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/invoices/list?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&page=0&size=20&sort=createdDate,DESC`


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
        "email": "479159321@qq.com"
    }
}

```

### 14.3.5 disableInvoice接口

- 功能描述:  根据id冲红蓝字发票
- 请求地址: `http://domain/customer/invoices/{id}`
- 请求动作: `DELETE`
- 请求示例: `http://domain/customer/invoices/64?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`


- 返回数据示例  
```
{
    "status": "SUCCESS"
}

```

### 14.3.5 resendEmail接口

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


### 14.3.6 createMonthBillInvoice接口

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


### 14.3.7 orders接口

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
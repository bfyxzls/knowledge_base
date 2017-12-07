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
	"isDefault":false,//默认状态
	"phoneNum":"手机号码"
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
	"isDefault":false,
	"phoneNum":"手机号码"
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


### 14.2 发票订单信息访问接口

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
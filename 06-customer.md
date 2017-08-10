# 6.1 Customer Controller接口

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
        "id": 1004,
        "realName": "张三",
        "nickname": "zz",
        "phoneNum": "12345678910",
        "email": "1221434@qq.com",
        "gender": 1,
        "vehicles": []
    }
}
```


### 6.1.3 上传用户头像接口

- 功能描述:  上传用户头像
- 请求地址: `http://domain/zuul/customer/customers/uploadAvatar/`
- 请求动作: `PUT`
- 请求示例: `http://domain/zuul/customer/customers/uploadAvatar?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
![Markdown](http://i1.buimg.com/1949/84c15df0a215c259.png)

- 请求数据示例  
```
{
    "id":1004
}
```

### 6.1.4 获取用户头像接口

- 功能描述:  获取用户头像
- 请求地址: `http://domain/customer/customers/{id}/avatar`
- 请求动作: `GET`
- 请求示例: `http://domain/customer/customers/1004/avatar?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例  

    ![Markdown](http://i2.kiimg.com/1949/7c84a20ddd1f1eaa.png)
    
    
    
### 6.1.5 绑定车辆接口

- 功能描述:  绑定车辆
- 请求地址: `http://domain/customer/customers/vehicleBinding`
- 请求动作: `PUT`
- 请求示例: `http://domain/customer/customers/vehicleBind?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 请求数据示例  
```
{
   "customerId":1004,
   "vehicleType":1,
   "carPlate":"皖A12345"，
   "vin":"123456"
}
```

### 6.1.5 解绑车辆接口

- 功能描述:  解绑车辆
- 请求地址: `http://domain/customer/customers/vehicleUnbinding`
- 请求动作: `PUT`
- 请求示例: `http://domain/customer/customers/vehicleUnbind?customerId=1004&vehicleId=1001&access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 请求数据示例  
```
{
    "status":true,
    "data":"车辆解绑成功"
}
```

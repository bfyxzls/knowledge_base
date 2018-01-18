## 10.1 app版本管理
### 10.1.1 发布新版本(Web)
- 功能描述: 发布新版本
- 请求地址: `http://domain/app/appVersions`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/app/appVersions?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`

   ```
     {
             	"code":"V1.0",
             	"type":"1",
             	"description":"新版本",
             	"url":"bb6abb6c-da9c-4dc1-9a87-5ee822056ac3.apk",
             	"name":"修改发送新版本"
             	
         	
         }
    ```
    - 备注：type为app类型，1为android，2为ios, 3为pos机
- 返回示例

  ```
  {
        "status": "SUCCESS"
    }
  ```
  
### 10.1.2 查询客户端历史版本分页列表(Web)

- 功能描述: 查询app历史版本分页列表
- 请求地址: `http://domain/app/appVersions?access_token&pageSize&pageNum`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/app/appVersions?access_token=df102429-f62d-461f-8a13-b4f08dce4c56&pageSize=10&pageNum=0`
- 返回参数:

```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1005,
                "code": "V1.0",
                "type": 1,
                "description": "新版本",
                "url": null,
                "updateTime": 1510106275059,
                "name": null
            },
            {
                "id": 1006,
                "code": "V1.0",
                "type": 1,
                "description": "新版本",
                "url": null,
                "updateTime": 1510107492757,
                "name": null
            },
            {
                "id": 1007,
                "code": "V1.0",
                "type": 1,
                "description": "新版本",
                "url": null,
                "updateTime": 1510133309119,
                "name": null
            },
            {
                "id": 1008,
                "code": "V1.0",
                "type": 1,
                "description": "新版本",
                "url": "bb6abb6c-da9c-4dc1-9a87-5ee822056ac3.apk",
                "updateTime": 1512438682981,
                "name": "修改发送新版本"
            }
        ],
        "totalElements": 4,
        "totalPages": 1,
        "last": true,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 4
    }
}
```

### 10.1.3 获取最新的app版本信息(App、Pos机)
- 功能描述: 获取最新的app版本信息
- 请求地址: `http://domain/app/appVersions/lastVersion?access_token&appType`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/app/appVersions/latestVersion?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431&appType=1`
- 返回参数:

```
{
    "status": "SUCCESS",
    "data": {
        "id": 1008,
        "code": "V1.0",
        "type": 1,
        "description": "新版本",
        "url": "bb6abb6c-da9c-4dc1-9a87-5ee822056ac3.apk",
        "updateTime": 1512438682981,
        "name": "修改发送新版本"
    }
}
```

### 10.1.4 上传apk安装包(Web)
- 功能描述: 上传apk安装包
- 请求地址: `http://domain/zuul/app/appVersions/uploadApk?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/zuul/app/appVersions/uploadApk?access_token=df102429-f62d-461f-8a13-b4f08dce4c56`
- 返回参数:

```
{
    "status": "SUCCESS"
}
```

### 10.1.5 下载apk安装包(android/pos)
- 功能描述: 下载apk安装包
- 请求地址: `http://domain/app/appVersions/downloadApk?access_token&apkFileName`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/app/appVersions/downloadApk?access_token=df102429-f62d-461f-8a13-b4f08dce4c56&apkFileName=d404f5fa-e3ac-4f02-85c9-71f3eb1716b9.apk`
- 返回参数: apk文件

## 10.2 反馈信息

### 10.2.1 app端新增反馈信息

- 功能描述: 新增反馈信息
- 请求地址: `http://domain/app/feedbacks?access_token=`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/app/feedbacks?access_token=df102429-f62d-461f-8a13-b4f08dce4c56`
- 请求示例：

```
{
    "status":1,
    "type":,
    "feedbackDate":"2018-1-17 12:00:00",
    "source":1， 1:app 2:小程序 3：公众号
    "description":"收费不合理"
}
```

### 10.2.2 app端查看反馈记录


- 功能描述: 查询用户反馈信息
- 请求地址: `http://domain/app/feedbacks/search?access_token=`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/app/feedbacks/search?access_token=df102429-f62d-461f-8a13-b4f08dce4c56`
- 返回示例：

```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1,
            "feedbackPhoneNum": "admin",
            "status": 1,
            "type": 1,
            "feedbackDate": "2018-01-17 12:00:00",
            "description": "收费不合理"
        },
        {
            "id": 2,
            "feedbackPhoneNum": "admin",
            "status": 1,
            "type": 1,
            "feedbackDate": "2018-01-18 12:00:00",
            "description": "收费太高"
        },
        {
            "id": 3,
            "feedbackPhoneNum": "admin",
            "status": 2,
            "type": 1,
            "feedbackDate": "2018-01-28 10:00:00",
            "description": "用户体验太差"
        }
    ]
}
```


### 10.2.2 web端模糊查询反馈记录


- 功能描述: 新增反馈信息
- 请求地址: `http://domain/app/feedbacks/query?access_token=`
- 请求动作: `GET`
- 请求示例: `http://localhost:8087/feedbacks/query?access_token=049fcb64-722c-4a43-8423-76b634ecdf19&feedbackPhoneNum&status&feedbackStartDate=2018-1-16&feedbackEndDate=2018-1-19&page=0&size=10&sort=feedbackDate,Desc`
- 请求示例：

```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 2,
                "feedbackPhoneNum": "admin",
                "status": 1,
                "type": 1,
                "feedbackDate": "2018-01-18 12:00:00",
                "description": "收费太高"
            },
            {
                "id": 1,
                "feedbackPhoneNum": "admin",
                "status": 1,
                "type": 1,
                "feedbackDate": "2018-01-17 12:00:00",
                "description": "收费不合理"
            }
        ],
        "pageable": {
            "sort": {
                "sorted": true,
                "unsorted": false
            },
            "offset": 0,
            "pageSize": 10,
            "pageNumber": 0,
            "unpaged": false,
            "paged": true
        },
        "last": true,
        "totalElements": 2,
        "totalPages": 1,
        "number": 0,
        "size": 10,
        "sort": {
            "sorted": true,
            "unsorted": false
        },
        "numberOfElements": 2,
        "first": true
    }
}
```



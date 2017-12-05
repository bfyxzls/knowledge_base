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


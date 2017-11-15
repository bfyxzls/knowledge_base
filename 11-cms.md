## 11.1资讯访问接口（InformationController）
### 9.1.1 新增资讯接口

- 功能描述:  新增资讯
- 请求地址: `http://domain/cms/informations`
- 请求动作: `POST`
- 请求示例: `http://domain/cms/informations?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 请求数据示例  
```
{
    "title":"标题",
    "subTitle":"副标题",
    "content":"内容",
    "status": 1, //发布状态：1.未发布；2.已发布
    "sort":111,//排序
    "ifTop":false,//是否置顶
    "type":1,//资讯类别：1.企业资讯；2.活动资讯；3.操作指南
    "titleImagePath":"标题文件名称",
    "ifPublish":true//是否发布
}
```

- 返回数据示例  
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "id": 30,
        "title": "标题",
        "subTitle": "副标题",
        "content": "内容",
        "status": 1,
        "sort": 111,
        "ifTop": false,
        "publishTime": 1510564019575,
        "type": 1,
        "titleImagePath": "1.jpg",
        "createdBy": "wyf",
        "createdDate": 1510564019613,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1510564019613
    }
}
```

### 9.1.2 通过id获取资讯信息

- 功能描述:  通过id获取资讯信息
- 请求地址: `http://domain/cms/informations/{id}`
- 请求动作: `GET`
- 请求示例: `http://domain/cms/informations/1?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例  
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "id": 30,
        "title": "标题",
        "subTitle": "副标题",
        "content": "内容",
        "status": 1,
        "sort": 111,
        "ifTop": false,
        "publishTime": 1510564019575,
        "type": 1,
        "titleImagePath": "1.jpg",
        "createdBy": "wyf",
        "createdDate": 1510564019613,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1510564019613
    }
}
```

### 9.1.3 修改资讯

- 功能描述:  修改资讯
- 请求地址: `http://domain/cms/informations/{id}`
- 请求动作: `PUT`
- 请求示例: `http://domain/cms/informations?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 请求数据示例  
```
{
    "title":"标题",
    "subTitle":"副标题",
    "content":"内容",
    "status": 1, //发布状态：1.未发布；2.已发布
    "sort":111,//排序
    "ifTop":false,//是否置顶
    "type":1,//资讯类别：1.企业资讯；2.活动资讯；3.操作指南
    "titleImagePath":"标题文件名称",
    "ifPublish":true//是否发布
}
```

- 返回数据示例  
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "id": 30,
        "title": "标题",
        "subTitle": "副标题",
        "content": "内容",
        "status": 1
        "sort": 111,
        "ifTop": false,
        "publishTime": 1510564019575,
        "type": 1,
        "titleImagePath": "1.jpg",
        "createdBy": "wyf",
        "createdDate": 1510564019613,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1510564019613
    }
}
```

#### 9.1.4 查询资讯列表

- 功能描述:  通过标题模糊匹配，发布时间之前及发布状态查询资讯列表
- 请求地址: `http://domain/cms/informations/query?access_token`
- 请求动作: `GET`
- 请求示例: `http://domain/cms/informations/query?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&title=&publishTime=&status=&type=`
- 参数说明： 
    - `title`: 标题
    - `publishTime`: 发布时间，格式：yyyy-MM-dd HH:mm:ss
    - `status`: 发布状态：1.未发布；2.已发布
    - `type`: 资讯类别：1.企业资讯；2.活动资讯；3.操作指南
   
- 返回数据示例  
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 29,
                "title": "测试新闻标题",
                "subTitle": "测试新闻副标题",
                "content": "测试新闻内容",
                "status": 1,
                "sort": 1,
                "ifTop": true,
                "publishTime": 1510106480695,
                "type": 1,
                "titleImagePath": null,
                "createdBy": "wyf",
                "createdDate": 1510106480727,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1510106480727
            },
            {
                "id": 30,
                "title": "测试新闻标题",
                "subTitle": "测试新闻副标题",
                "content": "测试新闻内容",
                "status": 1,
                "sort": 1,
                "ifTop": false,
                "publishTime": 1510564019575,
                "type": 1,
                "titleImagePath": null,
                "createdBy": "wyf",
                "createdDate": 1510564019613,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1510564019613
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 2,
        "size": 10,
        "number": 0,
        "first": true,
        "sort": null,
        "numberOfElements": 2
    }
}
```

#### 9.1.5 置顶资讯

- 功能描述:  通过id置顶资讯
- 请求地址: `http://domain/cms/informations/{id}/top`
- 请求动作: `PUT`
- 请求示例: `http://domain/cms/informations/1/top?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例  
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "id": 30,
        "title": "测试新闻标题",
        "subTitle": "测试新闻副标题",
        "content": "测试新闻内容",
        "status": 1,
        "sort": 1,
        "ifTop": true,
        "publishTime": 1510564019575,
        "type": 1,
        "titleImagePath": null,
        "createdBy": "wyf",
        "createdDate": 1510564019613,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1510564949561
    }
}
```

#### 9.1.6 上传资讯的图片

- 功能描述:  上传资讯的图片
- 请求地址: `http://domain/zuul/cms/informations/uploadImage`
- 请求动作: `POST`
- 请求示例: `http://domain/zuul/cms/informations/uploadImage?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`
  ![Markdown](http://i1.buimg.com/1949/84c15df0a215c259.png)
  
- 返回数据示例 
```$xslt
{
    "status": "SUCCESS",
    "data": "7c0b9fb4-fedc-483f-b7ab-3fd5d5e07327.jpg"
}
```

#### 9.1.7 删除资讯图片

- 功能描述:  删除资讯的图片
- 请求地址: `http://domain/cms/informations/deleteImage`
- 请求动作: `DELETE`
- 请求示例: `http://domain/cms/informations/deleteImage?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&name=
  ![Markdown](http://i1.buimg.com/1949/84c15df0a215c259.png)
  
- 返回数据示例 
```$xslt
{
    "status": "SUCCESS",
    "data": "7c0b9fb4-fedc-483f-b7ab-3fd5d5e07327.jpg"
}
```

#### 9.1.8 获取置顶资讯

- 功能描述:  获取置顶资讯
- 请求地址: `http://domain/cms/informations/queryTop`
- 请求动作: `GET`
- 请求示例: `http://domain/cms/informations/queryTop?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07`

- 返回数据示例  
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 29,
                "title": "测试新闻标题",
                "subTitle": "测试新闻副标题",
                "content": "测试新闻内容",
                "status": 1,
                "sort": 1,
                "ifTop": true,
                "publishTime": 1510106480695,
                "type": 1,
                "titleImagePath": null,
                "createdBy": "wyf",
                "createdDate": 1510106480727,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1510106480727
            },
            {
                "id": 30,
                "title": "测试新闻标题",
                "subTitle": "测试新闻副标题",
                "content": "测试新闻内容",
                "status": 1,
                "sort": 1,
                "ifTop": true,
                "publishTime": 1510564019575,
                "type": 1,
                "titleImagePath": null,
                "createdBy": "wyf",
                "createdDate": 1510564019613,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1510564949561
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 2,
        "size": 10,
        "number": 0,
        "first": true,
        "sort": null,
        "numberOfElements": 2
    }
}
```

#### 9.1.9 获取资讯图片
- 功能描述:  根据图片名称获取资讯图片
- 请求地址: `http://domain/cms/getInformationImage`
- 请求动作: `GET`
- 请求示例: `http://domain/cms/informations/getInformationImage?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&name=

- 返回数据示例  
![Markdown](http://i2.kiimg.com/1949/7c84a20ddd1f1eaa.png)

#### 9.1.10 通过资讯类型获取置顶资讯

- 功能描述:  通过资讯类型获取置顶资讯
- 请求地址: `http://domain/cms/informations/queryTopByType`
- 请求动作: `GET`
- 请求示例: `http://domain/cms/informations/queryTopByType?access_token=ef277fdb-6e80-433d-9155-9e6b58fa4e07&type=`
- 参数说明
    - `type`:资讯类别：1.企业资讯；2.活动资讯；3.操作指南

- 返回数据示例  
```$xslt
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 29,
            "title": "测试新闻标题",
            "subTitle": "测试新闻副标题",
            "titleImagePath": null,
            "type": 1
        },
        {
            "id": 30,
            "title": "测试新闻标题",
            "subTitle": "测试新闻副标题",
            "titleImagePath": null,
            "type": 1
        }
    ]
}
```
# 2.1 商业停车场信息访问接口
PS:需要用admin用户获得access_token
### 2.1.1 get接口
- 功能描述: 根据id查找商业停车场的信息
- 请求地址: `http://localhost:8080/infras/businessParkingAreas/{id}?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/businessParkingAreas/1028?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1028,
        "code": "999999",
        "name": "市府广场",
        "coordinate": {
            "type": "Point",
            "coordinates": [
                117.28652499621376,
                31.864361826772665
            ]
        },
        "parkingPositionQuantity": 3000,
        "maintainEnterprise": null,
        "province": "安徽省",
        "city": null,
        "district": "庐阳区",
        "isOwnBusiness": null,
        "unitPrice": 100,
        "remainParkingNum": 365,
        "createdBy": "wyf",
        "createdDate": 1501771401000,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1501771404000
    }
}
```
### 2.1.2 list接口
- 功能描述: 查商业停车场列表信息
- 请求地址: `http://localhost:8080/infras/businessParkingAreas?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/businessParkingAreas?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1037,
                "code": "3401030099",
                "name": "四十五中停车场",
                "coordinate": {
                    "type": "Point",
                    "coordinates": [
                        117.280767,
                        31.855289
                    ]
                },
                "parkingPositionQuantity": 200,
                "maintainEnterprise": null,
                "province": "安徽省",
                "city": "合肥市",
                "district": "庐阳区",
                "isOwnBusiness": null,
                "unitPrice": null,
                "remainParkingNum": null,
                "createdBy": "wyf",
                "createdDate": 1505113599782,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1505113599782
            }
        ],
        "last": false,
        "totalPages": 3,
        "totalElements": 56,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 20
    }
}
```
### 2.1.3 save接口
- 功能描述: 添加新的商业停车场信息
- 请求地址: `http://localhost:8080/infras/businessParkingAreas?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/infras/businessParkingAreas?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body：
```
{
               
    "code": "888",
    "name":  "万达广场",
    "coordinate": {
        "type": "Point",
        "coordinates": [
            12,
            67
        ]
    },
    "parkingPositionQuantity": 3000,
    "maintainEnterprise": null,
    "province": "安徽省",
    "city": "合肥市",
    "district": "庐阳区",
    "unitPrice": 100,
    "remainParkingNum": 365
}        
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1030,
        "code": "888",
        "name": "万达广场",
        "coordinate": {
            "type": "Point",
            "coordinates": [
                12,
                67
            ]
        },
        "parkingPositionQuantity": 3000,
        "maintainEnterprise": null,
        "province": "安徽省",
        "city": "合肥市",
        "district": "庐阳区",
        "isOwnBusiness": null,
        "unitPrice": 100,
        "remainParkingNum": 365,
        "createdBy": "wyf",
        "createdDate": 1501771401000,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1501771404000
    }
}
```
### 2.1.4 update接口
- 功能描述: 更新商业停车场信息
- 请求地址: `http://localhost:8080/infras/businessParkingAreas/{id}?access_token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/businessParkingAreas/1030?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body：
```
{               
    "code": "888",
    "name":  "万达广场",
    "coordinate": {
        "type": "Point",
        "coordinates": [
            12,
            77
        ]
    },
    "parkingPositionQuantity": 3000,
    "maintainEnterpriseId": 123,
    "province": "安徽省",
    "city": "合肥市",
    "district": "庐阳区",
    "isOwnBusiness": true,
    "unitPrice": 100,
    "remainParkingNum": 365,
}
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1030,
        "code": "888",
        "name": "万达广场",
        "coordinate": {
            "type": "Point",
            "coordinates": [
                12,
                77
            ]
        },
        "parkingPositionQuantity": 3000,
        "maintainEnterprise": null,
        "province": "安徽省",
        "city": "合肥市",
        "district": "庐阳区",
        "isOwnBusiness": null,
        "unitPrice": 100,
        "remainParkingNum": 365,
        "createdBy": "wyf",
        "createdDate": 1501771401000,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1501771404000
    }
}
```
### 2.1.5 queryByName接口
- 功能描述: 根据名字查询商业停车场信息
- 请求地址: `http://localhost:8080/infras/businessParkingAreas/query?access_token&name`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/businessParkingAreas/query?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=广场&page=0&size=20&sort=createdDate,DESC`
- 返回示例：
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1028,
                "code": "999999",
                "name": "市府广场",
                "coordinate": {
                    "type": "Point",
                    "coordinates": [
                        117.28652499621376,
                        31.864361826772665
                    ]
                },
                "parkingPositionQuantity": 3000,
                "maintainEnterprise": null,
                "province": "安徽省",
                "city": "合肥市",
                "district": "庐阳区",
                "isOwnBusiness": null,
                "unitPrice": 100,
                "remainParkingNum": 365,
                "createdBy": "wyf",
                "createdDate": 1501771401000,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1501771404000
            },
            {
                "id": 1029,
                "code": "999999",
                "name": "世界广场",
                "coordinate": {
                    "type": "Point",
                    "coordinates": [
                        100,
                        100
                    ]
                },
                "parkingPositionQuantity": 3000,
                "maintainEnterprise": null,
                "province": "安徽省",
                "city": "合肥市",
                "district": "庐阳区",
                "isOwnBusiness": null,
                "createdBy": "wyf",
                "createdDate": 1501771401000,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1501771404000
            },
            {
                "id": 1030,
                "code": "888",
                "name": "万达广场",
                "coordinate": {
                    "type": "Point",
                    "coordinates": [
                        12,
                        77
                    ]
                },
                "parkingPositionQuantity": 3000,
                "maintainEnterprise": null,
                "province": "安徽省",
                "city": "合肥市",
                "district": "庐阳区",
                "isOwnBusiness": null,
                "unitPrice": 100,
                "remainParkingNum": 365,
                "createdBy": "wyf",
                "createdDate": 1501771401000,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1501771404000
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 3,
        "number": 0,
        "size": 20,
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
        "numberOfElements": 3
    }
}

```
### 2.1.6 autoTop接口
- 功能描述: 根据名字自动提示查询商业停车场信息
- 请求地址: `http://localhost:8080/infras/businessParkingAreas/autoTop?access_token&name`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/businessParkingAreas/autoTop?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=广场`
- 返回示例：
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1028,
            "code": "999999",
            "name": "市府广场",
            "coordinate": {
                "type": "Point",
                "coordinates": [
                    117.28652499621376,
                    31.864361826772665
                ]
            },
            "parkingPositionQuantity": 3000,
            "maintainEnterprise": null,
            "province": "安徽省",
            "city": null,
            "district": "庐阳区",
            "isOwnBusiness": null,
            "unitPrice": 100,
            "remainParkingNum": 365,            
            "createdBy": "wyf",
            "createdDate": 1501771401000,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1501771404000
        },
        {
            "id": 1030,
            "code": "888",
            "name": "万达广场",
            "coordinate": {
                "type": "Point",
                "coordinates": [
                    117.25815110034199,
                    31.85328017017079
                ]
            },
            "parkingPositionQuantity": 3000,
            "maintainEnterprise": null,
            "province": "安徽省",
            "city": "",
            "district": "庐阳区",
            "isOwnBusiness": null,
            "unitPrice": 100,
            "remainParkingNum": 365,            
            "createdBy": "wyf",
            "createdDate": 1502886038323,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1502886038329
        },
        {
            "id": 1029,
            "code": "9999991",
            "name": "世界广场",
            "coordinate": {
                "type": "Point",
                "coordinates": [
                    117.26381592578127,
                    31.84701014558232
                ]
            },
            "parkingPositionQuantity": 3000,
            "maintainEnterprise": null,
            "province": "安徽省",
            "city": "",
            "district": "庐阳区",
            "isOwnBusiness": null,
            "unitPrice": 100,
            "remainParkingNum": 365,            
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        }
    ]
}
```
### 2.1.7 queryAllCoordinates接口

- 功能描述: 获取所有商业停车场坐标信息

- 请求地址: `http://localhost:8080/infras/businessParkingAreas/coordinates?access_token`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/infras/businessParkingAreas/coordinates?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`

- 返回示例：

```
  
  {
      "status": "SUCCESS",
      "data": [
          {
              "id": 1028,
              "coordinate": {
                  "type": "Point",
                  "coordinates": [
                      117.28652499621376,
                      31.864361826772665
                  ]
              }
          }
      ]
  }
```

  ​

### 2.1.8 app queryAllCoordinates接口

- 功能描述: app端获取所有商业停车场坐标信息

- 请求地址: `http://localhost:8080/infras/app/businessParkingAreas?access_token`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/infras/app/businessParkingAreas?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`

- 返回示例：

  ```json
  {
      "status": "SUCCESS",
      "data": [
          {
              "id": 1001,
              "name": "之心城",
              "coordinate": {
                  "type": "Point",
                  "coordinates": [
                      117.257089,
                      31.854264
                  ]
              },
              "totalParkingNum": 7000,
              "district": null,
              "usedParkingNum": 5657,
              "unitPrice": null,
              "code": "0000002"
          }
      ]
  }
  ```

### 2.1.9 queryCoordinatesByName接口

- 功能描述: 通过名称查询商业停车场坐标信息

- 请求地址: `http://localhost:8080/infras/businessParkingAreas/search?access_token&name`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/infras/businessParkingAreas/search?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=长江路`

- 返回示例：

  ```
  {
      "status": "SUCCESS",
      "data": [
          {
              "id": 1028,
              "coordinate": {
                  "type": "Point",
                  "coordinates": [
                      117.28652499621376,
                      31.864361826772665
                  ]
              }
          }
      ]
  }
  ```

  ​

### 2.1.10 app queryCoordinatesByName接口

- 功能描述: 通过名称查询商业停车场坐标信息

- 请求地址: `http://localhost:8080/infras/app/businessParkingAreas/search?access_token&name`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/infras/app/businessParkingAreas/search?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=长江路`

- 返回示例：

  ```json
  {
      "status": "SUCCESS",
      "data": [
          {
              "id": 1028,
              "coordinate": {
                  "type": "Point",
                  "coordinates": [
                      117.28652499621376,
                      31.864361826772665
                  ]
              }
          }
      ]
  }
  ```

  ​
### 2.1.11 app queryBusinessParkingAreaInfoById接口

- 功能描述: 通过商业停车场id查询商业停车场信息

- 请求地址: `http://localhost:8080/infras/app/businessParkingAreas/{id}?access_token`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/infras/app/businessParkingAreas/1030?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`

- 返回示例：

 ```
 {
     "status": "SUCCESS",
     "data": {
         "name": "万达广场",
         "id": 1030,
         "coordinate": {
             "type": "Point",
             "coordinates": [
                 12,
                 77
             ]
         },
         "district": "庐阳区",
         "totalParkingNum": 3000,
         "usedParkingNum": 0
     }
 }
 ```
### 2.1.12 商业停车场唯一性验证接口 
- 功能描述:  根据code查询停车场是否存在
- 请求地址: `http://localhost:8080/infras/businessParkingAreas?access_token=5709e4d3-49d1-4499-89c4-76905af9e87c&code=154146`
- 请求动作: `HEAD`
- 请求示例: `http://localhost:8080/infras/businessParkingAreas?access_token=5709e4d3-49d1-4499-89c4-76905af9e87c&code=154146`

- 返回用户示例  
```
返回信息包含在Response Header中：
isExist:true    已存在
isExist:false   不存在
```

### 2.1.13 remainParkingNum接口

- 功能描述:  更新商业停车场剩余车位
- 请求地址: `http://localhost:8080/infras/businessParkingAreas/remainParkingNum?code=0000003&remainParkingNum=10`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/businessParkingAreas/remainParkingNum?code=0000003&remainParkingNum=10`

- 返回用户示例  
```
    "status": "SUCCESS";
    "data": "更新商业停车场信息成功"
```

# 2.2 编码类型信息访问接口

### 2.2.1 get接口
- 功能描述: 根据id查找编码类型
- 请求地址: `http://localhost:8080/infras/codeTypes/{id}?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/codeTypes/1009?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1009,
        "name": "路段级别",
        "codes": [
            {
                "id": 1022,
                "value": "A级路段"
            },
            {
                "id": 1023,
                "value": "B级路段"
            }
        ],
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.2.2 List接口
- 功能描述: 查询编码类型列表信息
- 请求地址: `http://localhost:8080/infras/codeTypes?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/codeTypes?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1006,
                "name": "时间",
                "codes": [
                    {
                        "id": 1008,
                        "value": "年"
                    },
                    {
                        "id": 1009,
                        "value": "月"
                    },
                    {
                        "id": 1010,
                        "value": "日"
                    }
                ],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1008,
                "name": "性别",
                "codes": [
                    {
                        "id": 1014,
                        "value": "男"
                    },
                    {
                        "id": 1015,
                        "value": "女"
                    }
                ],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1009,
                "name": "路段级别",
                "codes": [
                    {
                        "id": 1022,
                        "value": "A级路段"
                    },
                    {
                        "id": 1023,
                        "value": "B级路段"
                    }
                ],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1010,
                "name": "职位",
                "codes": [
                    {
                        "id": 1024,
                        "value": "技术员"
                    },
                    {
                        "id": 1025,
                        "value": "收费员"
                    }
                ],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1013,
                "name": "货币单位",
                "codes": [
                    {
                        "id": 1035,
                        "value": "元"
                    },
                    {
                        "id": 1037,
                        "value": "分"
                    },
                    {
                        "id": 1036,
                        "value": "角"
                    }
                ],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1014,
                "name": "泊位类别",
                "codes": [
                    {
                        "id": 1044,
                        "value": "全日泊位"
                    }
                ],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1015,
                "name": "哈哈单位",
                "codes": [
                    {
                        "id": 1048,
                        "value": "毫米"
                    },
                    {
                        "id": 1049,
                        "value": "分"
                    },
                    {
                        "id": 1050,
                        "value": "角"
                    }
                ],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 7,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 7
    }
}

```
### 2.2.3 save接口
- 功能描述: 添加新的编码类型
- 请求地址: `http://localhost:8080/infras/codeTypes?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/infras/codeTypes?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{
    "name": "重量单位",
    "codes": [
        {
          
            "value": "磅"
        },
        {
           
            "value": "斤"
        },
        {
           
            "value": "公斤"
        }
    ]
}      
```
- 返回示例
```
 {
     "status": "SUCCESS",
     "data": {
         "id": 1018,
         "name": "重量单位",
         "codes": [
             {
                 "id": 1060,
                 "value": "磅"
             },
             {
                 "id": 1061,
                 "value": "斤"
             },
             {
                 "id": 1062,
                 "value": "公斤"
             }
         ],
         "createdBy": "wyf",
         "createdDate": 1502886018656,
         "lastModifiedBy": "wyf",
         "lastModifiedDate": 1504517002229
     }
 }
   
```
### 2.2.4 update接口
- 功能描述: 根据id更新编码类型信息
- 请求地址: `http://localhost:8080/infras/codeTypes/{id}?access_token`
- 请求动作: `put`
- 请求示例: `http://localhost:8080/infras/codeTypes/1018?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body
```
{ 
    "name":"saaaaa",
    "codes": [
        {        
            "id":1005,
            "value": "英磅"
        },
        {
            "id":1006,
            "value": "斤"
        },
        {
            "id":1007,           
            "value": "公斤"
        }
    ]
}

```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1018,
        "name": "重量单位",
        "codes": [
            {
                "id": 1066,
                "value": "英磅"
            },
            {
                "id": 1067,
                "value": "斤"
            },
            {
                "id": 1068,
                "value": "公斤"
            }
        ],
         "createdBy": "wyf",
         "createdDate": 1502886018656,
         "lastModifiedBy": "wyf",
         "lastModifiedDate": 1504517002229
    }
}

```
### 2.2.5 queryByName接口
- 功能描述: 根据名字查询编码类型信息
- 请求地址: `http://localhost:8080/infras/codeTypes/query?access_token&name`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/codeTypes/query?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=单位&page=0&size=20&sort=id,DESC`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1015,
                "name": "哈哈单位",
                "codes": [
                    {
                        "id": 1048,
                        "value": "毫米"
                    },
                    {
                        "id": 1049,
                        "value": "分"
                    },
                    {
                        "id": 1050,
                        "value": "角"
                    }
                ],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1013,
                "name": "面积单位",
                "codes": [
                    {
                        "id": 1051,
                        "value": "平方米"
                    },
                    {
                        "id": 1052,
                        "value": "平方厘米"
                    },
                    {
                        "id": 1053,
                        "value": "平方毫米"
                    }
                ],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1017,
                "name": "什么单位",
                "codes": [
                    {
                        "id": 1057,
                        "value": "平方米"
                    },
                    {
                        "id": 1058,
                        "value": "平方厘米"
                    },
                    {
                        "id": 1059,
                        "value": "平方毫米"
                    }
                ],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1018,
                "name": "重量单位",
                "codes": [
                    {
                        "id": 1066,
                        "value": "英磅"
                    },
                    {
                        "id": 1067,
                        "value": "斤"
                    },
                    {
                        "id": 1068,
                        "value": "公斤"
                    }
                ],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 4,
        "number": 0,
        "size": 20,
        "sort": [
                    {
                        "direction": "DESC",
                        "property": "id",
                        "ignoreCase": false,
                        "nullHandling": "NATIVE",
                        "ascending": false,
                        "descending": true
                    }
                ],
        "first": true,
        "numberOfElements": 4
    }
}

```
# 2.3 路段信息访问接口
### 2.3.1 get接口
- 功能描述: 根据id，查找路段信息
- 请求地址: `http://localhost:8080/infras/roadSections/{id}?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/roadSections/1020?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1020,
        "name": "潜山路-怀宁路",
        "level": 1023,
        "levelText": "B级路段",
        "coordinates": null,
        "parkingArea": null,
        "monthBillNum":100,
        "monthBillPrice":100,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.3.2 list接口
- 功能描述: 查询路段信息列表
- 请求地址: `http://localhost:8080/infras/roadSections?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/roadSections?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1020,
                "name": "潜山路-怀宁路",
                "level": 1023,
                "levelText": "B级路段",
                "coordinates": null,
                "parkingArea": null,
                "monthBillNum":100,
                "monthBillPrice":100,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1021,
                "name": "岳西路-长江西路",
                "level": 1022,
                "levelText": "A级路段",
                "coordinates": null,
                "parkingArea": null,
                "monthBillNum":100,
                "monthBillPrice":100,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 2,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 2
    }
}

```
### 2.3.3 save接口
- 功能描述:  添加新的路段信息
- 请求地址: `http://localhost:8080/infras/roadSections?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/infras/roadSections?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{               
    "name": "望江西路-创新大道",
    "level": 1023,
    "coordinates":,
    "unitPrice":1,
    "monthBillNum":10,
    "monthBillPrice":100,
    "parkingAreaId":1
}
       
```
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1022,
        "name": "望江西路-创新大道",
        "level": 1023,
        "levelText": "B级路段",
        "coordinates": null,
        "parkingArea": null,
        "unitPrice": 300,
        "monthBillNum":100,
        "monthBillPrice":100,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}
```
### 2.3.4 update接口
- 功能描述: 根据id更新路段信息
- 请求地址: `http://localhost:8080/infras/roadSections/{id}?access_token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/roadSections/1022?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{
                
    "name": "望江西路-创新大道",
    "level": 1023,
    "coordinate": {
            "type": "Point",
            "coordinates": [
                12,
                77
            ]
        },
    "parkingAreaId":123,
    "unitPrice": 300,
    "monthBillNum":100,
    "monthBillPrice":100
              
}
```
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1022,
        "name": "望江西路-创新大道",
        "level": 1023,
        "levelText": "SSS级路段",
        "coordinates": null,
        "parkingArea": null,
        "unitPrice": 300,
        "monthBillNum":100,
        "monthBillPrice":100,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}
```
### 2.3.5 queryByName接口
- 功能描述: 根据名字查询路段信息
- 请求地址: `http://localhost:8080/infras/roadSections/query?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/roadSections/query?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=望江西路-创新大道&page=0&size=20&sort=id,ASC`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1022,
                "name": "望江西路-创新大道",
                "level": 1023,
                "levelText": "B级路段",
                "coordinates": null,
                "parkingArea": null,
                "monthBillNum":100,
                "monthBillPrice":100,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 1,
        "number": 0,
        "size": 20,
        "sort": [
                    {
                        "direction": "DESC",
                        "property": "id",
                        "ignoreCase": false,
                        "nullHandling": "NATIVE",
                        "ascending": false,
                        "descending": true
                    }
                ],
        "first": true,
        "numberOfElements": 1
    }
}
```
### 2.3.6 autoTop接口
- 功能描述: 根据路段名自动提示查询匹配的路段信息
- 请求地址: `http://localhost:8080/infras/roadSections/autoTop?access_token&name`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/roadSections/autoTop?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca&name=路`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1020,
            "name": "潜山路-怀宁路",
            "level": 1023,
            "levelText": "B级路段",
            "coordinates": null,
            "parkingArea": null,
            "monthBillNum":100,
            "monthBillPrice":100,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        {
            "id": 1021,
            "name": "岳西路-长江西路",
            "level": 1022,
            "levelText": "A级路段",
            "coordinates": null,
            "parkingArea": null,
            "monthBillNum":100,
            "monthBillPrice":100,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        {
            "id": 1022,
            "name": "望江西路-创新大道",
            "level": 1023,
            "levelText": "B级路段",
            "coordinates": null,
            "parkingArea": null,
            "monthBillNum":100,
            "monthBillPrice":100,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        }
    ]
}
}
```
### 2.3.7 queryAllRoadSectionInfo接口

- 功能描述: 获取所有停车场坐标和泊位信息

- 请求地址: `http://localhost:8080/infras/roadSections/queryCoordinatesAndParkingStatus?access_token`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/infras/roadSections/queryCoordinatesAndParkingStatus?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`

- 返回示例:

  ```json
  {
      "status": "SUCCESS",
      "data": [
          {
              "id": 1022,
              "coordinates": {
                  "type": "MultiLineString",
                  "coordinates": [
                      [
                          [
                              117.19933306810447,
                              31.85425372612921
                          ],
                          [
                              117.20415567991324,
                              31.85509211848664
                          ]
                      ],
                      [
                          [
                              117.20410740015097,
                              31.855206029903528
                          ],
                          [
                              117.1993223392684,
                              31.854381308066642
                          ]
                      ]
                  ]
              },
              "usedParkingNum": 0,
              "totalParkingNum": 0
          }
        
      ]
  }
  ```

### 2.3.8 app queryAllRoadSectionInfo接口

- 功能描述: 获取所有停车场坐标和泊位信息

- 请求地址: `http://localhost:8080/infras/app/roadSections?access_token`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/infras/app/roadSections?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`

- 返回示例:

  ```json
  {
      "status": "SUCCESS",
      "data": [
          {
              "id": 1022,
              "name": "长江路",
              "coordinates": {
                  "type": "MultiLineString",
                  "coordinates": [
                      [
                          [
                              117.19933306810447,
                              31.85425372612921
                          ],
                          [
                              117.20415567991324,
                              31.85509211848664
                          ]
                      ],
                      [
                          [
                              117.20410740015097,
                              31.855206029903528
                          ],
                          [
                              117.1993223392684,
                              31.854381308066642
                          ]
                      ]
                  ]
              },
              "usedParkingNum": 0,
              "totalParkingNum": 0,
            	"unitPrice": 300
          }
      ]
  }
  ```

### 2.3.9 queryRoadSectionByName接口

- 功能描述: 根据名字查询匹配的停车场坐标和泊位信息

- 请求地址: `http://localhost:8080/infras/roadSections/search?access_token&name`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/infras/roadSections/search?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`

- 返回示例:

  ```json
  {
      "status": "SUCCESS",
      "data": [
          {
              "id": 1022,
              "coordinates": {
                  "type": "MultiLineString",
                  "coordinates": [
                      [
                          [
                              117.19933306810447,
                              31.85425372612921
                          ],
                          [
                              117.20415567991324,
                              31.85509211848664
                          ]
                      ],
                      [
                          [
                              117.20410740015097,
                              31.855206029903528
                          ],
                          [
                              117.1993223392684,
                              31.854381308066642
                          ]
                      ]
                  ]
              },
              "parkingNum": 0,
              "name": "长江路"
          },
          ...
      ]
  }
  ```

### 2.3.10 app queryRoadSectionByName接口

- 功能描述: app端根据名字查询匹配的停车场坐标和泊位信息

- 请求地址: `http://localhost:8080/infras/app/roadSections/search?access_token&name`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/infras/app/roadSections/search?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=长江路`

- 返回示例:

  ```json
  {
      "status": "SUCCESS",
      "data": [
          {
              "id": 1022,
              "coordinates": {
                  "type": "MultiLineString",
                  "coordinates": [
                      [
                          [
                              117.19933306810447,
                              31.85425372612921
                          ],
                          [
                              117.20415567991324,
                              31.85509211848664
                          ]
                      ],
                      [
                          [
                              117.20410740015097,
                              31.855206029903528
                          ],
                          [
                              117.1993223392684,
                              31.854381308066642
                          ]
                      ]
                  ]
              },
              "parkingNum": 0,
              "name": "长江路"
          }
      ]
  }
  ```

### 2.3.11 app queryRoadSectionInfoById接口

- 功能描述: app端根据路段id查询路段泊位信息

  - 请求地址: `http://localhost:8080/infras/app/roadSections/queryRoadSectionInfo?roadSectionId=1021&access_token`

  - 请求动作: `GET`

  - 请求示例: `http://localhost:8080/infras/app/roadSections/queryRoadSectionInfo?roadSectionId=1021&access_token=9d3af5fd-3e33-4d18-bafd-1317302bf826`

  - 返回示例:

 ```
 {
     "status": "SUCCESS",
     "data": {
         "id": 1030,
         "name": "岳西路-长江西路",
         "parkingAreaName": "潜山路-长江西路",
         "coordinates": {
             "type": "MultiLineString",
             "coordinates": [
                 [
                     [
                         117.19933306810447,
                         31.85425372612921
                     ],
                     [
                         117.20415567991324,
                         31.85509211848664
                     ]
                 ],
                 [
                     [
                         117.20410740015097,
                         31.855206029903528
                     ],
                     [
                         117.1993223392684,
                         31.854381308066642
                     ]
                 ]
             ]
         },
         "usedParkingNum": 12,
         "totalParkingNum": 11
     }
 }
 ```

### 2.3.12 通过id查询匹配的路段概要信息

- 功能描述：通过id查询匹配的路段概要信息
- 请求地址：`http://domain/infras/roadSections/{id}/generalInfo?access_token`
- 请求动作: `GET`
- 请求示例：`http://domain/infras/roadSections/1021/generalInfo?access_token=e10c62ae-3bc8-4938-bdbe-1465bf25c12a`
- 返回示例：

```
{
    "status": "SUCCESS",
    "data": {
        "id": 1021,
        "district": "蜀山区",
        "name": "岳西路-长江西路"
    }
}
```

### 2.3.13 根据路段查询所有岗位

- 功能描述：根据路段查询所有岗位
- 请求地址：`http://domain/infras/roadSections/{id}/posts?access_token`
- 请求动作: `GET`
- 请求示例：`http://domain/infras/roadSections/1021/posts?access_token=e10c62ae-3bc8-4938-bdbe-1465bf25c12a`
- 返回示例：

```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1020,
            "name": "岗位4"
        },
        {
            "id": 1021,
            "name": "岗位3"
        }
    ]
}
```

### 2.3.14 按区统计泊位数

- 功能描述：根据路段查询所有岗位

- 请求地址：`http://domain/infras/roadSections/obtainParkingNumGroupByDistrict?access_token`

- 请求动作: `GET`

- 请求示例：`http://domain/infras/roadSections/obtainParkingNumGroupByDistrict?access_token=e10c62ae-3bc8-4938-bdbe-1465bf25c12a`

- 返回示例：

  ```json
  {
      "status": "SUCCESS",
      "data": {
      	"totalNum":0,
        "parkingNumStats":[
      	    {
                "district":"蜀山区",
                "parkingNum":0
        	}
      	    ]
      }
  }
  ```

  ​

# 2.4 泊位信息访问接口



### 2.4.1 get接口
- 功能描述: 根据id查询泊位信息
- 请求地址: `http://localhost:8080/infras/parkings/{id}?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/parkings/1017?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1017,
        "code": "154140",
        "post": {
            "id": 1014,
            "name": "岗位1",
            "direction": 1,
            "coordinates": null,
            "parkingType": 1,
            "parkingDistribution": 1,
            "roadSection": null,
            "employees": [],
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        "type": null,
        "typeText": null,
        "arrangementDirection": 1,
        "chargingStrategy": null,
        "sortCode":151144,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}
```
### 2.4.2 list接口
- 功能描述: 查找泊位信息列表
- 请求地址: `http://localhost:8080/infras/parkings?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/parkings?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1017,
                "code": "154140",
                "post": {
                    "id": 1014,
                    "name": "岗位1",
                    "direction": 1,
                    "coordinates": null,
                    "parkingType": 1,
                    "parkingDistribution": 1,
                    "roadSection": null,
                    "employees": [],
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "type": null,
                "typeText": null,
                "arrangementDirection": 1,
                "chargingStrategy": null,
                "sortCode":151144,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1018,
                "code": "154141",
                "post": {
                    "id": 1014,
                    "name": "岗位1",
                    "direction": 1,
                    "coordinates": null,
                    "parkingType": 1,
                    "parkingDistribution": 1,
                    "roadSection": null,
                    "employees": [],
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "type": null,
                "typeText": null,
                "arrangementDirection": 1,
                "chargingStrategy": null,
                "sortCode":151144,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 4,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 4
    }
}

```
### 2.4.3 save接口
- 功能描述: 添加新的泊位信息
- 请求地址: `http://localhost:8080/infras/parkings?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/infras/parkings?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{
   
    "code": "154147",
    "post": {
        "id" : "1015",
        "name": "岗位007",
        "direction": 1,
        "coordinates": null,
        "parkingType": 1,
        "parkingDistribution": 1,
        "employees": []      
        }                 
}      
```
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1023,
        "code": "154147",
        "post": {
            "id": 1015,
            "name": "岗位007",
            "direction": 1,
            "coordinates": null,
            "parkingType": 1,
            "parkingDistribution": 1,
            "roadSection": null,
            "employees": [],
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        "type": null,
        "typeText": null,
        "arrangementDirection": null,
        "chargingStrategy": null,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}
```
### 2.4.4 update接口
- 功能描述: 根据id更新泊位信息
- 请求地址: `http://localhost:8080/infras/parkings/{id}?access_token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/parkings/1031?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{       
    "code": "22222",
    "postId": 123,
    "type":1,
    "arrangementDirection":2,
    "chargingStrategy":3
 }
```
-返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1031,
        "code": "154151",
        "post": {
            "id": 1014,
            "name": "岗位11",
            "direction": 1,
            "coordinates": null,
            "parkingType": 1,
            "parkingDistribution": 1,
            "roadSection": null,
            "createdBy": "wyf",
            "createdDate": 1502706611000,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1502706617000
        },
        "type": null,
        "typeText": null,
        "arrangementDirection": null,
        "chargingStrategy": null,
        "sortCode": 154151,
        "createdBy": "wyf",
        "createdDate": 1502114054000,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1502114054000
    }
}
```
### 2.4.5 queryByCode接口
- 功能描述: 根据编码查询停车场信息
- 请求地址: `http://localhost:8080/infras/parkings/query?access_token&code`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/parkings/query?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&code=154155&page=0&size=20&sort=sortCode,DESC`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1035,
                "code": "154155",
                "post": {
                    "id": 1020,
                    "name": "岗位4",
                    "direction": 1,
                    "coordinates": {
                        "type": "MultiLineString",
                        "coordinates": [
                            [
                                [
                                    117.23114397386678,
                                    31.847996220026925
                                ],
                                [
                                    117.23119225362905,
                                    31.846328412456177
                                ]
                            ],
                            [
                                [
                                    117.23104741434224,
                                    31.847968879162345
                                ],
                                [
                                    117.23111715177663,
                                    31.846314741777725
                                ]
                            ]
                        ]
                    },
                    "parkingType": 2,
                    "parkingDistribution": 1,
                    "roadSection": {
                        "id": 1020,
                        "name": "潜山路-怀宁路",
                        "level": 1023,
                        "levelText": "B级路段",
                        "coordinates": {
                            "type": "MultiLineString",
                            "coordinates": [
                                [
                                    [
                                        117.19933306810447,
                                        31.85425372612921
                                    ],
                                    [
                                        117.20415567991324,
                                        31.85509211848664
                                    ]
                                ],
                                [
                                    [
                                        117.20410740015097,
                                        31.855206029903528
                                    ],
                                    [
                                        117.1993223392684,
                                        31.854381308066642
                                    ]
                                ]
                            ]
                        },
                        "parkingArea": {
                            "id": 1037,
                            "code": "700000",
                            "name": "岳西路停车场",
                            "coordinates": {
                                "type": "MultiLineString",
                                "coordinates": [
                                    [
                                        [
                                            117.19933306810447,
                                            31.85425372612921
                                        ],
                                        [
                                            117.20415567991324,
                                            31.85509211848664
                                        ]
                                    ],
                                    [
                                        [
                                            117.20410740015097,
                                            31.855206029903528
                                        ],
                                        [
                                            117.1993223392684,
                                            31.854381308066642
                                        ]
                                    ]
                                ]
                            },
                            "parkingPositionQuantity": 600,
                            "maintainEnterprise": null,
                            "province": "安徽省",
                            "city": "",
                            "district": "蜀山区",
                            "createdBy": "wyf",
                            "createdDate": 1501771500000,
                            "lastModifiedBy": "wyf",
                            "lastModifiedDate": 1504572445649
                        },
                        "parkingNum": 2,
                        "createdBy": "wyf",
                        "createdDate": 1501809923000,
                        "lastModifiedBy": "wyf",
                        "lastModifiedDate": 1503731330726
                    },
                    "createdBy": "wyf",
                    "createdDate": 1502706609000,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1502706616000
                },
                "type": null,
                "typeText": null,
                "arrangementDirection": 2,
                "chargingStrategy": null,
                "sortCode": 154155,
                "createdBy": "wyf",
                "createdDate": 1503483640681,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1503483640728
            }
        ],
        "totalPages": 1,
        "totalElements": 1,
        "last": true,
        "number": 0,
        "size": 20,
        "sort": [
            {
                "direction": "DESC",
                "property": "sortCode",
                "ignoreCase": false,
                "nullHandling": "NATIVE",
                "ascending": false,
                "descending": true
            }
        ],
        "first": true,
        "numberOfElements": 1
    }
}

```
### 2.4.6 根据泊位编码查询所属岗位id

- 功能描述: 根据泊位编码查询所属岗位id
- 请求地址: `http://localhost:8080/infras/parkings/{code}/post?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/parkings/154142/post?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:

```json
{
    "status": "SUCCESS",
    "data": {
        "postId": 1014
    }
}
```

### 2.4.7 泊位唯一性验证接口 
- 功能描述:  根据code查询泊位是否存在
- 请求地址: `http://localhost:8080/infras/parkings?access_token=5709e4d3-49d1-4499-89c4-76905af9e87c&code=154146`
- 请求动作: `HEAD`
- 请求示例: `http://localhost:8080/infras/parkings?access_token=5709e4d3-49d1-4499-89c4-76905af9e87c&code=154146`

- 返回用户示例  
```
返回信息包含在Response Header中：
isExist:true    已存在
isExist:false   不存在
```



# 2.5 企业信息访问接口

### 2.5.1 get接口
- 功能描述: 根据id查询企业信息
- 请求地址: `http://localhost:8080/infras/enterprises/{id}?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/enterprises/1003?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1003,
        "name": "合肥城市泊车投资管理有限公司",
        "abbr": "合肥城泊",
        "type": null,
        "contactPerson": "",
        "contactPersonPhoneNum": "",
        "contactPersonEmail": "",
        "province": "安徽省",
        "city": "合肥市",
        "district": "庐阳区",
        "address": "劳动局5楼",
        "parentEnterprise": null,
        "sort": null,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.5.2 list接口
- 功能描述: 查询企业信息列表
- 请求地址: `http://localhost:8080/infras/enterprises?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/enterprises?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```

    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1003,
                "name": "合肥城市泊车投资管理有限公司",
                "abbr": "合肥城泊",
                "type": null,
                "contactPerson": "",
                "contactPersonPhoneNum": "",
                "contactPersonEmail": "",
                "province": "安徽省",
                "city": "合肥市",
                "district": "庐阳区",
                "address": "劳动局5楼",
                "parentEnterprise": null,
                "sort": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1004,
                "name": "",
                "abbr": "",
                "type": null,
                "contactPerson": "",
                "contactPersonPhoneNum": "",
                "contactPersonEmail": "",
                "province": "",
                "city": "",
                "district": "",
                "address": "",
                "parentEnterprise": null,
                "sort": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1005,
                "name": "合肥城市泊车投资管理有限公司全资子公司",
                "abbr": "合肥城泊分公司1",
                "type": null,
                "contactPerson": "",
                "contactPersonPhoneNum": "",
                "contactPersonEmail": "",
                "province": "安徽省",
                "city": "合肥市",
                "district": "庐阳区",
                "address": "劳动局10楼",
                "parentEnterprise": null,
                "sort": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalElements": 3,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 3
    }
}

```
### 2.5.3 save接口
- 功能描述: 添加新的企业信息
- 请求地址: `http://localhost:8080/infras/enterprises?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/infras/enterprises?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{
    "name": "合肥城市泊车投资管理有限公司全资子公司",
    "abbr": "合肥城泊分公司",
    "type": null,
    "contactPerson": "",
    "contactPersonPhoneNum": "",
    "contactPersonEmail": "",
    "province": "安徽省",
    "city": "合肥市",
    "district": "庐阳区",
    "address": "劳动局10楼",
    "parentEnterprise": null
}
```
- 返回示例：
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1006,
        "name": "合肥城市泊车投资管理有限公司全资子公司",
        "abbr": "合肥城泊分公司",
        "type": null,
        "contactPerson": "",
        "contactPersonPhoneNum": "",
        "contactPersonEmail": "",
        "province": "安徽省",
        "city": "合肥市",
        "district": "庐阳区",
        "address": "劳动局10楼",
        "parentEnterprise": null,
        "sort": null,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.5.4 update接口
- 功能描述: 根据id更新企业信息
- 请求地址: `http://localhost:8080/infras/enterprises/{id}?access_token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/enterprises/1005?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{       
        "abbr": "合肥城泊分公司1" ,
        "name":"zhang",
         "type":1,
         "contactPerson":"zhang",
         "contactPersonPhoneNum":"zhang",
         "contactPersonEmail":"1231@11.com",
         "province":"hefei",
         "city":"hefei",
         "district":"qu",
         "address":"zhang",
         "parentEnterpriseId":112,
         "sort":12
}
```
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1005,
        "name": "合肥城市泊车投资管理有限公司全资子公司",
        "abbr": "合肥城泊分公司1",
        "type": null,
        "contactPerson": "",
        "contactPersonPhoneNum": "",
        "contactPersonEmail": "",
        "province": "安徽省",
        "city": "合肥市",
        "district": "庐阳区",
        "address": "劳动局10楼",
        "parentEnterprise": null,
        "sort": null,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.5.5 queryByName接口
- 功能描述: 根据名字查询企业信息
- 请求地址: `http://localhost:8080/infras/enterprises/query?access_token&name`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/enterprises/query?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=合肥城市泊车投资管理有限公司全资子公司&page=0&size=20&sort=sort,DESC`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1006,
                "name": "合肥城市泊车投资管理有限公司全资子公司",
                "abbr": "合肥城泊分公司",
                "type": null,
                "contactPerson": "",
                "contactPersonPhoneNum": "",
                "contactPersonEmail": "",
                "province": "安徽省",
                "city": "合肥市",
                "district": "庐阳区",
                "address": "劳动局10楼",
                "parentEnterprise": null,
                "sort": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1005,
                "name": "合肥城市泊车投资管理有限公司全资子公司",
                "abbr": "合肥城泊分公司1",
                "type": null,
                "contactPerson": "",
                "contactPersonPhoneNum": "",
                "contactPersonEmail": "",
                "province": "安徽省",
                "city": "合肥市",
                "district": "庐阳区",
                "address": "劳动局10楼",
                "parentEnterprise": null,
                "sort": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalElements": 2,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": [
                    {
                        "direction": "DESC",
                        "property": "sort",
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
### 2.5.6 autoTop接口
- 功能描述: 根据名字查询匹配的企业信息
- 请求地址: `http://localhost:8080/infras/enterprises/autoTop?access_token&name`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/enterprises/autoTop?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=合肥城市泊车投资管理有限公司全资子公司`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1006,
            "name": "合肥城市泊车投资管理有限公司全资子公司",
            "abbr": "合肥城泊分公司",
            "type": null,
            "contactPerson": "",
            "contactPersonPhoneNum": "",
            "contactPersonEmail": "",
            "province": "安徽省",
            "city": "合肥市",
            "district": "庐阳区",
            "address": "劳动局10楼",
            "parentEnterprise": null,
            "sort": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        {
            "id": 1005,
            "name": "合肥城市泊车投资管理有限公司全资子公司",
            "abbr": "合肥城泊分公司1",
            "type": null,
            "contactPerson": "",
            "contactPersonPhoneNum": "",
            "contactPersonEmail": "",
            "province": "安徽省",
            "city": "合肥市",
            "district": "庐阳区",
            "address": "劳动局10楼",
            "parentEnterprise": null,
            "sort": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        }
    ]
}

```
# 2.6 停车场信息访问接口
### 2.6.1 get接口
- 功能描述: 根据id查找停车场信息
- 请求地址: `http://localhost:8080/infras/parkingAreas/{id}?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/parkingAreas/1037?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1037,
        "code": "700000",
        "name": "岳西路停车场",
        "coordinates": null,
        "parkingPositionQuantity": 600,
        "maintainEnterprise": null,
        "province": "安徽省",
        "city": "合肥市",
        "district": "蜀山区",
         "bizParkingAreaType":2,
         "tags":["在线缴费"], 
         "openingHour":"7:00-22:00",
          "bizParkingAreaChargeDtos": [
                     {
                         "fee": 0,
                         "hour": "15分钟"
                     },
                     {
                         "fee": 5,
                         "hour": "1小时"
                     },
                     {
                         "fee": 7,
                         "hour": "3小时"
                     },
                     {
                         "fee": 9,
                         "hour": "5小时"
                     },
                     {
                         "fee": 10,
                         "hour": "封顶"
                     }
                 ]   
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.6.2 list接口
- 功能描述: 查询停车场信息列表
- 请求地址: `http://localhost:8080/infras/parkingAreas?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/parkingAreas?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1036,
                "code": "340001",
                "name": "长江西路停车场",
                "coordinates": {
                    "type": "MultiLineString",
                    "coordinates": [
                        [
                            [
                                117.26717843927491,
                                31.879240046583675
                            ],
                            [
                                117.2720922461902,
                                31.87938581497547
                            ]
                        ],
                        [
                            [
                                117.26740374483222,
                                31.878966730227376
                            ],
                            [
                                117.2720922461902,
                                31.87919449391393
                            ]
                        ]
                    ]
                },
                "parkingPositionQuantity": 1111,
                "maintainEnterprise": null,
                "province": "安徽省",
                "city": "合肥市",
                "district": "蜀山区",
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1038,
                "code": "700000",
                "name": "岳东路停车场",
                "coordinates": null,
                "parkingPositionQuantity": 600,
                "maintainEnterprise": null,
                "province": "安徽省",
                "city": "合肥市",
                "district": "蜀山区",
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1037,
                "code": "700000",
                "name": "岳西路停车场",
                "coordinates": null,
                "parkingPositionQuantity": 600,
                "maintainEnterprise": null,
                "province": "安徽省",
                "city": "北京市",
                "district": "蜀山区",
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229}
            }
        ],
        "last": true,
        "totalElements": 3,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 3
    }
}
```
### 2.6.3 save接口
- 功能描述: 添加新的停车场信息
- 请求地址: `http://localhost:8080/infras/parkingAreas?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/infras/parkingAreas?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{               
    "code": "700000",
    "name": "岳东路停车场",
    "coordinates": null,
    "parkingPositionQuantity": 600,
    "maintainEnterpriseId": 123,
    "province": "安徽省",
    "city": "合肥市",
    "district": "蜀山区",
    "bizParkingAreaType":2,
    "tags":["在线缴费"], 
    "openingHour":"7:00-22:00"      
}
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1039,
        "code": "700000",
        "name": "岳东路停车场",
        "coordinates": null,
        "parkingPositionQuantity": 600,
        "maintainEnterprise": null,
        "province": "安徽省",
        "city": "合肥市",
        "district": "蜀山区",
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.6.4 update接口
- 功能描述: 根据id更新停车场信息
- 请求地址: `http://localhost:8080/infras/parkingAreas/{id}?access_token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/parkingAreas/1037?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{  
    "city": "北京市"  
}
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1037,
        "code": "700000",
        "name": "岳西路停车场",
        "coordinates": null,
        "parkingPositionQuantity": 600,
        "maintainEnterprise": null,
        "province": "安徽省",
        "city": "北京市",
        "district": "蜀山区",
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.6.5 queryByName接口
- 功能描述: 根据名字查询停车场信息
- 请求地址: `http://localhost:8080/infras/parkingAreas/query?access_token&name`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/parkingAreas/query?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=长江西路停车场&page=0&size=20&sort=code,DESC`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1036,
                "code": "340001",
                "name": "长江西路停车场",
                "coordinates": {
                    "type": "MultiLineString",
                    "coordinates": [
                        [
                            [
                                117.26717843927491,
                                31.879240046583675
                            ],
                            [
                                117.2720922461902,
                                31.87938581497547
                            ]
                        ],
                        [
                            [
                                117.26740374483222,
                                31.878966730227376
                            ],
                            [
                                117.2720922461902,
                                31.87919449391393
                            ]
                        ]
                    ]
                },
                "parkingPositionQuantity": 1111,
                "maintainEnterprise": null,
                "province": "安徽省",
                "city": "合肥市",
                "district": "蜀山区",
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalElements": 1,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": [
                    {
                        "direction": "DESC",
                        "property": "code",
                        "ignoreCase": false,
                        "nullHandling": "NATIVE",
                        "ascending": false,
                        "descending": true
                    }
                ],
        "first": true,
        "numberOfElements": 1
    }
}
```
### 2.6.6 autoTop接口
- 功能描述: 根据名字查询匹配的停车场信息
- 请求地址: `http://localhost:8080/infras/parkingAreas/autoTop?access_token&name`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/parkingAreas/autoTop?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=岳东路停车场`
- 返回示例:

 ```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1038,
            "code": "700000",
            "name": "岳东路停车场",
            "coordinates": null,
            "parkingPositionQuantity": 600,
            "maintainEnterprise": null,
            "province": "安徽省",
            "city": "合肥市",
            "district": "蜀山区",
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        {
            "id": 1039,
            "code": "700000",
            "name": "岳东路停车场",
            "coordinates": null,
            "parkingPositionQuantity": 600,
            "maintainEnterprise": null,
            "province": "安徽省",
            "city": "合肥市",
            "district": "蜀山区",
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        }
    ]
}
 ```

 ### 2.6.7 路边停车场唯一性验证接口 
- 功能描述:  根据code查询路边停车场是否存在
- 请求地址: `http://localhost:8080/infras/parkingAreas?access_token=5709e4d3-49d1-4499-89c4-76905af9e87c&code=154146`
- 请求动作: `HEAD`
- 请求示例: `http://localhost:8080/infras/parkingAreas?access_token=5709e4d3-49d1-4499-89c4-76905af9e87c&code=154146`

- 返回用户示例  
```
返回信息包含在Response Header中：
isExist:true    已存在
isExist:false   不存在
```

 

# 2.7 岗位信息访问接口
### 2.7.1 get接口
- 功能描述: 根据id查询岗位信息
- 请求地址: `http://localhost:8080/infras/posts/{id}?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/posts/1014?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1014,
        "name": "岗位1",
        "direction": 1,
        "coordinates": null,
        "parkingType": 1,
        "parkingDistribution": 1,
        "roadSection": {
            "id": 1021,
            "name": "岳西路-长江西路",
            "level": 1022,
            "levelText": "A级路段",
            "coordinates": null,
            "parkingArea": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        "employees": [],
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.7.2 list接口
- 功能描述: 查询岗位信息列表
- 请求地址: `http://localhost:8080/infras/posts?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/posts?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1014,
                "name": "岗位1",
                "direction": 1,
                "coordinates": null,
                "parkingType": 1,
                "parkingDistribution": 1,
                "roadSection": {
                    "id": 1021,
                    "name": "岳西路-长江西路",
                    "level": 1022,
                    "levelText": "A级路段",
                    "coordinates": null,
                    "parkingArea": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "employees": [],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229}
            },
            {
                "id": 1015,
                "name": "岗位2",
                "direction": 1,
                "coordinates": null,
                "parkingType": 2,
                "parkingDistribution": 1,
                "roadSection": {
                    "id": 1020,
                    "name": "潜山路-怀宁路",
                    "level": 1023,
                    "levelText": "B级路段",
                    "coordinates": null,
                    "parkingArea": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "employees": [],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1020,
                "name": "岗位3",
                "direction": 1,
                "coordinates": null,
                "parkingType": 2,
                "parkingDistribution": 1,
                "roadSection": {
                    "id": 1020,
                    "name": "潜山路-怀宁路",
                    "level": 1023,
                    "levelText": "B级路段",
                    "coordinates": null,
                    "parkingArea": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "employees": [],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalElements": 3,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 3
    }
}

```
### 2.7.3 save接口
- 功能描述: 添加新的岗位信息
- 请求地址: `http://localhost:8080/infras/posts?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/infras/posts?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{  
    "name": "岗位3",
    "direction": 1,
    "coordinates": null,
    "parkingType": 2,
    "parkingDistribution": 1,
    "roadSection": {
        "id": 1020
    },
    "employees": []
}
```
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1021,
        "name": "岗位3",
        "direction": 1,
        "coordinates": null,
        "parkingType": 2,
        "parkingDistribution": 1,
        "roadSection": {
            "id": 1020,
            "name": "潜山路-怀宁路",
            "level": 1023,
            "levelText": "B级路段",
            "coordinates": null,
            "parkingArea": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        "employees": [],
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.7.4 update接口
- 功能描述: 根据id更新岗位信息
- 请求地址: `http://localhost:8080/infras/posts/{id}?access_token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/posts/1015?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{  
    "name": "123" ,  
    "direction": 2 ,  
    "coordinates": null ,  
    "parkingType": 2 ,  
    "parkingDistribution": 2 ,  
    "roadSectionId": 2             
}
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1015,
        "name": "岗位2",
        "direction": 1,
        "coordinates": null,
        "parkingType": 2,
        "parkingDistribution": 1,
        "roadSection": {
            "id": 1020,
            "name": "潜山路-怀宁路",
            "level": 1023,
            "levelText": "B级路段",
            "coordinates": null,
            "parkingArea": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        "employees": [],
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.7.5 queryByParkingAreaName接口
- 功能描述: 根据路段名查询岗位信息
- 请求地址: `http://localhost:8080/infras/posts/query?access_token&roadSectionName`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/posts/query?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&parkingAreaName=岳西路&page=0&size=20&sort=id,DESC`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1014,
                "name": "岗位1",
                "direction": 1,
                "coordinates": null,
                "parkingType": 1,
                "parkingDistribution": 1,
                "roadSection": {
                    "id": 1021,
                    "name": "岳西路-长江西路",
                    "level": 1022,
                    "levelText": "A级路段",
                    "coordinates": null,
                    "parkingArea": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "employees": [],
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalElements": 1,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": [
                    {
                        "direction": "DESC",
                        "property": "id",
                        "ignoreCase": false,
                        "nullHandling": "NATIVE",
                        "ascending": false,
                        "descending": true
                    }
                ],
        "first": true,
        "numberOfElements": 1
    }
}

```
### 2.7.6 autoTop接口
- 功能描述: 根据路段名查询岗位信息
- 请求地址: `http://localhost:8080/infras/posts/autoTop?access_token&roadSectionName`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/posts/autoTop?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&roadSectionName=潜山路-怀宁路`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1020,
            "name": "岗位3",
            "direction": 1,
            "coordinates": null,
            "parkingType": 2,
            "parkingDistribution": 1,
            "roadSection": {
                "id": 1020,
                "name": "潜山路-怀宁路",
                "level": 1023,
                "levelText": "B级路段",
                "coordinates": null,
                "parkingArea": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            "employees": [],
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        {
            "id": 1021,
            "name": "岗位3",
            "direction": 1,
            "coordinates": null,
            "parkingType": 2,
            "parkingDistribution": 1,
            "roadSection": {
                "id": 1020,
                "name": "潜山路-怀宁路",
                "level": 1023,
                "levelText": "B级路段",
                "coordinates": null,
                "parkingArea": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            "employees": [],
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        {
            "id": 1015,
            "name": "岗位2",
            "direction": 1,
            "coordinates": null,
            "parkingType": 2,
            "parkingDistribution": 1,
            "roadSection": {
                "id": 1020,
                "name": "潜山路-怀宁路",
                "level": 1023,
                "levelText": "B级路段",
                "coordinates": null,
                "parkingArea": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            "employees": [],
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        }
    }
}

```
### 2.7.7 获取指定岗位下的所有员工信息

- 功能描述：获取指定岗位下的所有员工信息
- 请求地址：`http://domain/infras/posts/{id}/employees?access_token`
- 请求动作: `GET`
- 请求示例：`http://domain/infras/posts/1014/employees?access_token=e10c62ae-3bc8-4938-bdbe-1465bf25c12a`
- 返回示例：

```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1001,
            "name": "佘能斌",
            "postName": "岗位11",
            "phoneNum": "18621061991"
        }
    ]
}
```



# 2.8 部门信息访问接口

### 2.8.1 get接口
- 功能描述: 根据id查询部门信息
- 请求地址: `http://localhost:8080/infras/depts/{id}?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/depts/1003?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1003,
        "name": "人力资源部",
        "abbr": "人力",
        "enterprise": {
            "id": 1003,
            "name": "合肥城市泊车投资管理有限公司",
            "abbr": "合肥城泊",
            "type": null,
            "contactPerson": "",
            "contactPersonPhoneNum": "",
            "contactPersonEmail": "",
            "province": "安徽省",
            "city": "合肥市",
            "district": "庐阳区",
            "address": "劳动局5楼",
            "parentEnterprise": null,
            "sort": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        "personInCharge": "zz",
        "parentDept": null,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}
```
### 2.8.2 list接口
- 功能描述: 查询部门信息列表
- 请求地址: `http://localhost:8080/infras/depts?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/depts?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1003,
                "name": "人力资源部",
                "abbr": "人力",
                "enterprise": {
                    "id": 1003,
                    "name": "合肥城市泊车投资管理有限公司",
                    "abbr": "合肥城泊",
                    "type": null,
                    "contactPerson": "",
                    "contactPersonPhoneNum": "",
                    "contactPersonEmail": "",
                    "province": "安徽省",
                    "city": "合肥市",
                    "district": "庐阳区",
                    "address": "劳动局5楼",
                    "parentEnterprise": null,
                    "sort": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "personInCharge": "zz",
                "parentDept": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1005,
                "name": "情报部门",
                "abbr": "情报",
                "enterprise": {
                    "id": 1003,
                    "name": "合肥城市泊车投资管理有限公司",
                    "abbr": "合肥城泊",
                    "type": null,
                    "contactPerson": "",
                    "contactPersonPhoneNum": "",
                    "contactPersonEmail": "",
                    "province": "安徽省",
                    "city": "合肥市",
                    "district": "庐阳区",
                    "address": "劳动局5楼",
                    "parentEnterprise": null,
                    "sort": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "personInCharge": null,
                "parentDept": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1004,
                "name": "清洁部门",
                "abbr": "情报",
                "enterprise": {
                    "id": 1003,
                    "name": "合肥城市泊车投资管理有限公司",
                    "abbr": "合肥城泊",
                    "type": null,
                    "contactPerson": "",
                    "contactPersonPhoneNum": "",
                    "contactPersonEmail": "",
                    "province": "安徽省",
                    "city": "合肥市",
                    "district": "庐阳区",
                    "address": "劳动局5楼",
                    "parentEnterprise": null,
                    "sort": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "personInCharge": null,
                "parentDept": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 3,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 3
    }
}
```
### 2.8.3 save接口
- 功能描述: 添加新的部门信息
- 请求地址: `http://localhost:8080/infras/depts?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/infras/depts?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{
    "name": "情报部门",
    "abbr": "情报",
    "enterprise": {
        "id": 1003 
     }
 }
```
-  返回示例：
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1006,
        "name": "情报部门",
        "abbr": "情报",
        "enterprise": {
            "id": 1003,
            "name": "合肥城市泊车投资管理有限公司",
            "abbr": "合肥城泊",
            "type": null,
            "contactPerson": "",
            "contactPersonPhoneNum": "",
            "contactPersonEmail": "",
            "province": "安徽省",
            "city": "合肥市",
            "district": "庐阳区",
            "address": "劳动局5楼",
            "parentEnterprise": null,
            "sort": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        "personInCharge": null,
        "parentDept": null,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.8.4 update接口
- 功能描述: 根据id更新部门信息
- 请求地址: `http://localhost:8080/infras/depts/{id}?access_token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/depts/1004?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`       
- Body:
```
{
    "name": "清洁部门",
    "abbr": "情报",
    "enterpriseId": 123,
    "personInCharge": "123",
    "parentDeptId": 123                                                                                         
}               
```
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1004,
        "name": "清洁部门",
        "abbr": "情报",
        "enterprise": {
            "id": 1003,
            "name": "合肥城市泊车投资管理有限公司",
            "abbr": "合肥城泊",
            "type": null,
            "contactPerson": "",
            "contactPersonPhoneNum": "",
            "contactPersonEmail": "",
            "province": "安徽省",
            "city": "合肥市",
            "district": "庐阳区",
            "address": "劳动局5楼",
            "parentEnterprise": null,
            "sort": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        "personInCharge": null,
        "parentDept": null,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.8.5 queryByName接口
- 功能描述: 根据部门名字查询匹配的所有部门信息
- 请求地址: `http://localhost:8080/infras/depts/query?access_token&name`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/depts/query?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=清洁&page=0&size=20&sort=id,DESC`      
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1004,
                "name": "清洁部门",
                "abbr": "情报",
                "enterprise": {
                    "id": 1003,
                    "name": "合肥城市泊车投资管理有限公司",
                    "abbr": "合肥城泊",
                    "type": null,
                    "contactPerson": "",
                    "contactPersonPhoneNum": "",
                    "contactPersonEmail": "",
                    "province": "安徽省",
                    "city": "合肥市",
                    "district": "庐阳区",
                    "address": "劳动局5楼",
                    "parentEnterprise": null,
                    "sort": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "personInCharge": null,
                "parentDept": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 1,
        "number": 0,
        "size": 20,
        "sort": [
                    {
                        "direction": "DESC",
                        "property": "id",
                        "ignoreCase": false,
                        "nullHandling": "NATIVE",
                        "ascending": false,
                        "descending": true
                    }
                ],
        "first": true,
        "numberOfElements": 1
    }
}

```
### 2.8.6 autoTop接口
- 功能描述: 根据部门名字自动提示匹配的部门信息
- 请求地址: `http://localhost:8080/infras/depts/autoTop?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/depts/autoTop?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&name=部门`  
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1005,
            "name": "情报部门",
            "abbr": "情报",
            "enterprise": {
                "id": 1003,
                "name": "合肥城市泊车投资管理有限公司",
                "abbr": "合肥城泊",
                "type": null,
                "contactPerson": "",
                "contactPersonPhoneNum": "",
                "contactPersonEmail": "",
                "province": "安徽省",
                "city": "合肥市",
                "district": "庐阳区",
                "address": "劳动局5楼",
                "parentEnterprise": null,
                "sort": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            "personInCharge": null,
            "parentDept": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        {
            "id": 1006,
            "name": "情报部门",
            "abbr": "情报",
            "enterprise": {
                "id": 1003,
                "name": "合肥城市泊车投资管理有限公司",
                "abbr": "合肥城泊",
                "type": null,
                "contactPerson": "",
                "contactPersonPhoneNum": "",
                "contactPersonEmail": "",
                "province": "安徽省",
                "city": "合肥市",
                "district": "庐阳区",
                "address": "劳动局5楼",
                "parentEnterprise": null,
                "sort": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            "personInCharge": null,
            "parentDept": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        {
            "id": 1004,
            "name": "清洁部门",
            "abbr": "情报",
            "enterprise": {
                "id": 1003,
                "name": "合肥城市泊车投资管理有限公司",
                "abbr": "合肥城泊",
                "type": null,
                "contactPerson": "",
                "contactPersonPhoneNum": "",
                "contactPersonEmail": "",
                "province": "安徽省",
                "city": "合肥市",
                "district": "庐阳区",
                "address": "劳动局5楼",
                "parentEnterprise": null,
                "sort": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            "personInCharge": null,
            "parentDept": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        }
    ]
}

```
# 2.9 编码信息访问接口
### 2.9.1 get接口
- 功能描述: 根据id查找编码与编码类型名
- 请求地址: `http://localhost:8080/infras/dictionaries/getCodes?access_token&codeTypeId`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/dictionaries/getCodes?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee&codeTypeId=1006`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1008,
            "value": "年"
        },
        {
            "id": 1009,
            "value": "月"
        },
        {
            "id": 1010,
            "value": "日"
        }
    ]
}
```
# 2.10 雇员信息访问接口
### 2.10.1 get接口
- 功能描述: 根据id查找雇员信息
- 请求地址: `http://localhost:8080/infras/employees/{id}?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/employees/1005?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1005,
        "name": "小六",
        "gender": 2,
        "dept": null,
        "position": null,
        "positionText": null,
        "phoneNum": null,
        "sort": null,
        "defaultPost": null,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}
```
### 2.10.2 list接口
- 功能描述: 查询雇员信息列表
- 请求地址: `http://localhost:8080/infras/employees?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/employees?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1001,
                "name": "佘能斌",
                "gender": 1,
                "dept": {
                    "id": 1003,
                    "name": "人力资源部",
                    "abbr": "人力",
                    "enterprise": {
                        "id": 1003,
                        "name": "合肥城市泊车投资管理有限公司",
                        "abbr": "合肥城泊",
                        "type": null,
                        "contactPerson": "",
                        "contactPersonPhoneNum": "",
                        "contactPersonEmail": "",
                        "province": "安徽省",
                        "city": "合肥市",
                        "district": "庐阳区",
                        "address": "劳动局5楼",
                        "parentEnterprise": null,
                        "sort": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                    },
                    "personInCharge": "zz",
                    "parentDept": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "position": 1025,
                "positionText": "收费员",
                "phoneNum": "18621061991",
                "sort": null,
                "defaultPost": {
                    "id": 1014,
                    "name": "岗位1",
                    "direction": 1,
                    "coordinates": null,
                    "parkingType": 1,
                    "parkingDistribution": 1,
                    "roadSection": {
                        "id": 1021,
                        "name": "岳西路-长江西路",
                        "level": 1022,
                        "levelText": "A级路段",
                        "coordinates": null,
                        "parkingArea": null,
                        "createdBy": "wyf",
                        "createdDate": 1502886018656,
                        "lastModifiedBy": "wyf",
                        "lastModifiedDate": 1504517002229
                    },
                    "employees": [],
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1002,
                "name": "赵朋飞",
                "gender": 2,
                "dept": null,
                "position": null,
                "positionText": null,
                "phoneNum": null,
                "sort": null,
                "defaultPost": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1003,
                "name": "赵朋飞",
                "gender": 2,
                "dept": null,
                "position": null,
                "positionText": null,
                "phoneNum": null,
                "sort": null,
                "defaultPost": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1004,
                "name": "刘鹏飞",
                "gender": 2,
                "dept": {
                    "id": 1003,
                    "name": "人力资源部",
                    "abbr": "人力",
                    "enterprise": {
                        "id": 1003,
                        "name": "合肥城市泊车投资管理有限公司",
                        "abbr": "合肥城泊",
                        "type": null,
                        "contactPerson": "",
                        "contactPersonPhoneNum": "",
                        "contactPersonEmail": "",
                        "province": "安徽省",
                        "city": "合肥市",
                        "district": "庐阳区",
                        "address": "劳动局5楼",
                        "parentEnterprise": null,
                        "sort": null,
                        "createdBy": "wyf",
                        "createdDate": 1502886018656,
                        "lastModifiedBy": "wyf",
                        "lastModifiedDate": 1504517002229
                    },
                    "personInCharge": "zz",
                    "parentDept": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "position": null,
                "positionText": null,
                "phoneNum": null,
                "sort": null,
                "defaultPost": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1005,
                "name": "小六",
                "gender": 2,
                "dept": null,
                "position": null,
                "positionText": null,
                "phoneNum": null,
                "sort": null,
                "defaultPost": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            {
                "id": 1006,
                "name": "小V",
                "gender": 2,
                "dept": null,
                "position": null,
                "positionText": null,
                "phoneNum": null,
                "sort": null,
                "defaultPost": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalElements": 6,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 6
    }
}

```
### 2.10.3 save接口
- 功能描述: 添加新的雇员信息
- 请求地址: `http://localhost:8080/infras/employees?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/infras/employees?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{
    "id": 1005,
    "name": "小六",
    "gender": 2,
    "dept": null,
    "position": null,
    "positionText": null,
    "phoneNum": null,
    "sort": null,
    "defaultPost": null,  
}
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1005,
        "name": "小六",
        "gender": 2,
        "dept": null,
        "position": null,
        "positionText": null,
        "phoneNum": null,
        "sort": null,
        "defaultPost": null,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}

```
### 2.10.4 update接口
- 功能描述: 根据id更新雇员信息
- 请求地址: `http://localhost:8080/infras/employees/{id}?access_token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/employees/1005?access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`
- Body:
```
{
    "name": "123",
    "gender": 1,
    "deptId": 2,
    "position": 1005,
    "phoneNum": "小吧",
    "sort": 2,
    "defaultPostId": 2   
}

```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1005,
        "name": "小吧",
        "gender": 2,
        "dept": null,
        "position": null,
        "positionText": null,
        "phoneNum": null,
        "sort": null,
        "defaultPost": null,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}
```
### 2.10.5 queryByNameAndPhoneNum接口
- 功能描述: 根据姓名或电话查询雇员信息
- 请求地址: `http://localhost:8080/infras/employees/query?access_token`
         或 `http://localhost:8080/infras/employees/query?access_token&name`
         或 `http://localhost:8080/infras/employees/query?access_token&name&phoneNum`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/employees/query?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca&name=佘能斌&page=0&size=20&sort=sort,DESC`
- 返回示例:
```
{   
   "status": "SUCCESS",
   "data": {
       "content": [
           {
               "id": 1001,
               "name": "佘能斌",
               "gender": 1,
               "dept": {
                   "id": 1003,
                   "name": "人力资源部",
                   "abbr": "人力",
                   "enterprise": {
                       "id": 1003,
                       "name": "合肥城市泊车投资管理有限公司",
                       "abbr": "合肥城泊",
                       "type": null,
                       "contactPerson": "",
                       "contactPersonPhoneNum": "",
                       "contactPersonEmail": "",
                       "province": "安徽省",
                       "city": "合肥市",
                       "district": "庐阳区",
                       "address": "劳动局5楼",
                       "parentEnterprise": null,
                       "sort": null,
                        "createdBy": "wyf",
                        "createdDate": 1502886018656,
                        "lastModifiedBy": "wyf",
                        "lastModifiedDate": 1504517002229
                   },
                   "personInCharge": "zz",
                   "parentDept": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
               },
               "position": 1025,
               "username": "zhang",
               "positionText": "收费员",
               "phoneNum": "18621061991",
               "sort": null,
               "defaultPost": {
                   "id": 1014,
                   "name": "岗位1",
                   "direction": 1,
                   "coordinates": null,
                   "parkingType": 1,
                   "parkingDistribution": 1,
                   "roadSection": {
                       "id": 1021,
                       "name": "岳西路-长江西路",
                       "level": 1022,
                       "levelText": "A级路段",
                       "coordinates": null,
                       "parkingArea": null,
                        "createdBy": "wyf",
                        "createdDate": 1502886018656,
                        "lastModifiedBy": "wyf",
                        "lastModifiedDate": 1504517002229
                   },
                   "employees": [],
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
               },
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
           }
       ],
       "last": true,
       "totalPages": 1,
       "totalElements": 1,
       "number": 0,
       "size": 20,
        "sort": [
                    {
                        "direction": "DESC",
                        "property": "id",
                        "ignoreCase": false,
                        "nullHandling": "NATIVE",
                        "ascending": false,
                        "descending": true
                    }
                ],
       "first": true,
       "numberOfElements": 1
   }
   
}
```

### 2.10.6 autoTop接口
- 功能描述: 根据员工名字自动提示匹配的员工信息
- 请求地址: `http://localhost:8080/infras/employees/autoTop?name=123&access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/employees/autoTop?name=飞&access_token=f1235ff1-521b-4ec3-add0-6c7c894ec4ee`  
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1002,
            "name": "赵朋飞",
            "gender": 2,
            "dept": null,
            "position": 1024,
            "positionText": "技术员",
            "phoneNum": "66666",
            "sort": null,
            "defaultPost": {
                "id": 1021,
                "name": "岗位3",
                "direction": 1,
                "coordinates": null,
                "parkingType": 2,
                "parkingDistribution": 1,
                "roadSection": {
                    "id": 1020,
                    "name": "潜山路-怀宁路",
                    "level": 1023,
                    "levelText": "B级路段",
                    "coordinates": {
                        "type": "MultiLineString",
                        "coordinates": [
                            [
                                [
                                    117.19933306810447,
                                    31.85425372612921
                                ],
                                [
                                    117.20415567991324,
                                    31.85509211848664
                                ]
                            ],
                            [
                                [
                                    117.20410740015097,
                                    31.855206029903528
                                ],
                                [
                                    117.1993223392684,
                                    31.854381308066642
                                ]
                            ]
                        ]
                    },
                    "parkingArea": {
                        "id": 1037,
                        "code": "700000",
                        "name": "岳西路停车场",
                        "coordinates": {
                            "type": "MultiLineString",
                            "coordinates": [
                                [
                                    [
                                        117.19933306810447,
                                        31.85425372612921
                                    ],
                                    [
                                        117.20415567991324,
                                        31.85509211848664
                                    ]
                                ],
                                [
                                    [
                                        117.20410740015097,
                                        31.855206029903528
                                    ],
                                    [
                                        117.1993223392684,
                                        31.854381308066642
                                    ]
                                ]
                            ]
                        },
                        "parkingPositionQuantity": 600,
                        "maintainEnterprise": null,
                        "province": "安徽省",
                        "city": null,
                        "district": "蜀山区",
                        "createdBy": "wyf",
                        "createdDate": 1501771500000,
                        "lastModifiedBy": "wyf",
                        "lastModifiedDate": 1501771487000
                    },
                    "parkingNum": 5,
                    "createdBy": "wyf",
                    "createdDate": 1501809923000,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1502111609414
                },
                "createdBy": "wyf",
                "createdDate": 1502706613000,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1502706619000
            },
            "createdBy": "wyf",
            "createdDate": 1502704527000,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1502706438000
        },
        {
            "id": 1003,
            "name": "赵朋飞",
            "gender": 2,
            "dept": null,
            "position": null,
            "positionText": null,
            "phoneNum": null,
            "sort": null,
            "defaultPost": null,
            "createdBy": "wyf",
            "createdDate": 1502703840000,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1502706446000
        },
        {
            "id": 1004,
            "name": "刘鹏飞",
            "gender": 2,
            "dept": null,
            "position": null,
            "positionText": null,
            "phoneNum": null,
            "sort": null,
            "defaultPost": null,
            "createdBy": "wyf",
            "createdDate": 1502704503000,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1502706448000
        }
    ]
}

```

### 2.10.7 员工获取个人信息
- 功能描述: 员工获取个人信息
- 请求地址: `http://localhost:8080/infras/employees/selfInfo?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/employees/selfInfo?access_token=8fcc7df5-caf8-4ef8-a70f-1ee955c9f2b3`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "postId": 1000,
        "postName": "1号岗",
        "roadSectionId": 1003,
        "roadSectionName": "潜山路",
        "parkingAreaName": "植保路",
        "district": "蜀山区",
        "employeeId": 1003,
        "employeeName": "张齐健",
        "employeePhoneNum": "15555471960"
    }
}
```

# 2.11 SIM卡信息访问接口

### 2.11.1 根据id查询SIM卡信息接口

- 功能描述: 根据id查询SIM卡信息
- 请求地址: `http://localhost:8080/infras/sims/{id}?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/sims/1000?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1000,
        "iccid": "12397183091",
        "operator_type": 1079,
        "operator": "中国电信",
        "phoneNum": null,
        "snCode": null,
        "equipment_type": 1080,
        "equipmentText": "POS机",
        "equipmentCode": null,
        "dept": {
            "id": 1003,
            "name": "人力资源部",
            "abbr": "人力",
            "enterprise": null,
            "personInCharge": "zz",
            "parentDept": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        "status": 1072,
        "statusText": "使用中",
        "remark": null,
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}
```

### 2.11.2 查询所有SIM卡信息接口

- 功能描述: 查询所有SIM卡信息
- 请求地址: `http://localhost:8080/infras/sims?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/sims?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1000,
                "iccid": "12397183091",
                "operator_type": 1079,
                "operator": "中国电信",
                "phoneNum": null,
                "snCode": null,
                "equipment_type": 1080,
                "equipmentText": "POS机",
                "equipmentCode": null,
                "dept": {
                    "id": 1003,
                    "name": "人力资源部",
                    "abbr": "人力",
                    "enterprise": null,
                    "personInCharge": "zz",
                    "parentDept": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "status": 1072,
                "statusText": "使用中",
                "remark": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalElements": 1,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "first": true,
        "sort": null,
        "numberOfElements": 1
    }
}
```

### 2.11.3 新增SIM卡接口

- 功能描述: 新增SIM卡
- 请求地址: `http://localhost:8080/infras/sims?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/infras/sims?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`
- 请求示例:
```
{
	"iccid":"12397183091",
	"operator_type":1079,
	"equipment_type":1080,
	"dept":{
		"id":1007
	},
	"status":1072
}
```

### 2.11.4 更新SIM卡接口

- 功能描述: 更新SIM卡信息
- 请求地址: `http://localhost:8080/infras/sims/{id}?access_token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/sims/1000?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`
- 请求示例:
```
{	
    "iccid": "123",
    "operator": 1,
    "phoneNum": "1213",
    "snCode": "1231",
    "equipment": 1,
    "equipmentCode": "123",
    "deptId": 2 ,
    "status": 2,
    "remark": "2e213"     
}
```

### 2.11.5 条件查询SIM卡接口

- 功能描述: 按iccid和SN码查询SIM卡信息
- 请求地址: `http://localhost:8080/infras/sims/query?iccid=123&snCode=456?access_token2fbd327e-3fc9-43f9-8227-3c4f121d00ca`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/sims/query?iccid=123&access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca&page=0&size=20&sort=id,DESC`
         或`http://localhost:8080/infras/sims/query?snCode=456&access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca&page=0&size=20&sort=id,DESC`
         或`http://localhost:8080/infras/sims/query?iccid=123&snCode=456&access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca&page=0&size=20&sort=id,DESC`
- 请求示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1000,
                "iccid": "123971830",
                "operator_type": 1079,
                "operator": "中国电信",
                "phoneNum": null,
                "snCode": "999",
                "equipment_type": 1080,
                "equipmentText": "POS机",
                "equipmentCode": null,
                "dept": {
                    "id": 1003,
                    "name": "人力资源部",
                    "abbr": "人力",
                    "enterprise": null,
                    "personInCharge": "zz",
                    "parentDept": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "status": 1072,
                "statusText": "使用中",
                "remark": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalElements": 1,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": [
                    {
                        "direction": "DESC",
                        "property": "id",
                        "ignoreCase": false,
                        "nullHandling": "NATIVE",
                        "ascending": false,
                        "descending": true
                    }
                ],
        "first": true,
        "numberOfElements": 1
    }
}
```

### 2.11.6 条件查询未关联的SIM卡

- 功能描述: 根据iccid模糊查询未关联的SIM卡
- 请求地址: `http://localhost:8081/sims/unrelated?access_token=ec00544b-7c11-448c-a75e-9e22a08fc1b9&iccid=5`
- 请求动作: `GET`
- 请求示例: `http://localhost:8081/sims/unrelated?access_token=ec00544b-7c11-448c-a75e-9e22a08fc1b9&iccid=5`
         
- 请求示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1005,
                "iccid": "12345"
            },
            {
                "id": 1000,
                "iccid": "14567"
            }
        ],
        "pageable": {
            "sort": {
                "sorted": false,
                "unsorted": true
            },
            "offset": 0,
            "pageSize": 20,
            "pageNumber": 0,
            "unpaged": false,
            "paged": true
        },
        "last": true,
        "totalPages": 1,
        "totalElements": 2,
        "number": 0,
        "size": 20,
        "sort": {
            "sorted": false,
            "unsorted": true
        },
        "numberOfElements": 2,
        "first": true
    }
}
```


# 2.12 POS机信息访问接口

### 2.12.1 根据id查询POS机信息接口

- 功能描述: 根据id查询POS机信息
- 请求地址: `http://localhost:8080/infras/poses/{id}?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/poses/1001?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1001,
        "code": "123456",
        "imei": "ada21",
        "version_type": 1070,
        "version": "4G",
        "producer_id": null,
        "producer": null,
        "dept": {
            "id": 1007,
            "name": "合肥城泊技术部",
            "abbr": "技术部",
            "enterprise": null,
            "personInCharge": "黄欢",
            "parentDept": {
                "id": 1003,
                "name": "人力资源部",
                "abbr": "人力",
                "enterprise": null,
                "personInCharge": "zz",
                "parentDept": null,
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            },
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        "status": 1072,
        "statusText": "使用中",
        "remark": null,
        "employee": {
            "id": 1004,
            "name": "刘鹏飞",
            "gender": 2,
            "dept": null,
            "position": null,
            "positionText": null,
            "phoneNum": null,
            "sort": null,
            "defaultPost": null,
            "createdBy": "wyf",
            "createdDate": 1502886018656,
            "lastModifiedBy": "wyf",
            "lastModifiedDate": 1504517002229
        },
        "createdBy": "wyf",
        "createdDate": 1502886018656,
        "lastModifiedBy": "wyf",
        "lastModifiedDate": 1504517002229
    }
}
```

### 2.12.2 查询所有POS机信息接口

- 功能描述: 查询所有POS机信息
- 请求地址: `http://localhost:8080/infras/poses?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/poses?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1001,
                "code": "123456",
                "imei": "ada21",
                "version_type": 1070,
                "version": "4G",
                "producer_id": null,
                "producer": null,
                "dept": {
                    "id": 1007,
                    "name": "合肥城泊技术部",
                    "abbr": "技术部",
                    "enterprise": null,
                    "personInCharge": "黄欢",
                    "parentDept": {
                        "id": 1003,
                        "name": "人力资源部",
                        "abbr": "人力",
                        "enterprise": null,
                        "personInCharge": "zz",
                        "parentDept": null,
                        "createdBy": "wyf",
                        "createdDate": 1502886018656,
                        "lastModifiedBy": "wyf",
                        "lastModifiedDate": 1504517002229
                    },
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "status": 1072,
                "statusText": "使用中",
                "remark": null,
                "employee": {
                    "id": 1004,
                    "name": "刘鹏飞",
                    "gender": 2,
                    "dept": null,
                    "position": null,
                    "positionText": null,
                    "phoneNum": null,
                    "sort": null,
                    "defaultPost": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalElements": 1,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "first": true,
        "sort": null,
        "numberOfElements": 1
    }
}
```

### 2.12.3 新增POS机接口

- 功能描述: 新增POS机
- 请求地址: `http://localhost:8080/infras/poses?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/infras/poses?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`
- 请求示例:
```
{
	"code":"12313",
	"imei":"ada21",
	"producer":1079,
	"status":1020,
	"version":1019,
	"simIccid": "1213"
}
```

### 2.12.4 更新POS机接口

- 功能描述: 更新POS机信息
- 请求地址: `http://localhost:8080/infras/poses/{id}?access_token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/poses/1000?access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca`
- 请求示例:
```
{
    "code": "213123",
    "imei": "1213",
    "version": 1,
    "producer": 1,
    "deptId": 123,
    "status": 2 ,
    "remark": "q231",
    "employeeId": 123,
    "simIccid": "1213"
}
```

### 2.12.5 条件查询POS机接口

- 功能描述: 按Pos机编号和使用者姓名查询Pos机信息
- 请求地址: `http://localhost:8080/infras/poses/query?code=123&employeeName=456?access_token2fbd327e-3fc9-43f9-8227-3c4f121d00ca`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/infras/poses/query?code=123&access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca&page=0&size=20&sort=id,DESC`
         或`http://localhost:8080/infras/poses/query?employeeName=456&access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca&page=0&size=20&sort=id,DESC`
         或`http://localhost:8080/infras/poses/query?code=123&employeeName=456&access_token=2fbd327e-3fc9-43f9-8227-3c4f121d00ca&page=0&size=20&sort=id,DESC`
- 请求示例:
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1001,
                "code": "123456",
                "imei": "ada21",
                "version_type": 1070,
                "version": "4G",
                "producer_id": null,
                "producer": null,
                "dept": {
                    "id": 1007,
                    "name": "合肥城泊技术部",
                    "abbr": "技术部",
                    "enterprise": null,
                    "personInCharge": "黄欢",
                    "parentDept": {
                        "id": 1003,
                        "name": "人力资源部",
                        "abbr": "人力",
                        "enterprise": null,
                        "personInCharge": "zz",
                        "parentDept": null,
                        "createdBy": "wyf",
                        "createdDate": 1502886018656,
                        "lastModifiedBy": "wyf",
                        "lastModifiedDate": 1504517002229
                    },
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
                },
                "status": 1072,
                "statusText": "使用中",
                "remark": null,
                "employee": {
                    "id": 1004,
                    "name": "刘鹏飞",
                    "gender": 2,
                    "dept": null,
                    "position": null,
                    "positionText": null,
                    "phoneNum": null,
                    "sort": null,
                    "defaultPost": null,
                    "createdBy": "wyf",
                    "createdDate": 1502886018656,
                    "lastModifiedBy": "wyf",
                    "lastModifiedDate": 1504517002229
                },
                "createdBy": "wyf",
                "createdDate": 1502886018656,
                "lastModifiedBy": "wyf",
                "lastModifiedDate": 1504517002229
            }
        ],
        "last": true,
        "totalElements": 1,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": [
                    {
                        "direction": "DESC",
                        "property": "id",
                        "ignoreCase": false,
                        "nullHandling": "NATIVE",
                        "ascending": false,
                        "descending": true
                    }
                ],
        "first": true,
        "numberOfElements": 1
    }
}
```

# 2.13 Districts信息访问接口
### 2.13.1 查询所有的区名
- 功能描述: App端购买月票时显示所有的区以及其下的停车场信息
- 请求地址: `http://localhost:8080/infras/districts?access_token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/infras/districts?access_token=69ff3003-dee1-40d5-a36f-c0c4fa55c431`
- 返回示例:
```
{
    "status": "SUCCESS",
    "data": [
        {
            "name": "庐阳区",
            "parkingAreaDtos": []
        },
        {
            "name": "蜀山区",
            "parkingAreaDtos": [
                {
                    "id": 1000,
                    "name": "植保路"
                },
                {
                    "id": 1002,
                    "name": "岳东路停车场"
                }
            ]
        },
        {
            "name": "包河区",
            "parkingAreaDtos": []
        },
        {
            "name": "瑶海区",
            "parkingAreaDtos": []
        },
        {
            "name": "庐江县",
            "parkingAreaDtos": []
        },
        {
            "name": "肥东县",
            "parkingAreaDtos": [
                {
                    "id": 1001,
                    "name": "888"
                },
                {
                    "id": 1003,
                    "name": "岳东路停车场"
                },
                {
                    "id": 1004,
                    "name": "岳东路停车场"
                }
            ]
        },
        {
            "name": "肥西县",
            "parkingAreaDtos": []
        }
    ]
}
```
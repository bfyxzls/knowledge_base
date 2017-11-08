## 10.1 app版本管理
### 10.1.1 发布新版本
- 功能描述: 发布新版本
- 请求地址: `http://domain/app/appVersions?access_token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/app/appVersions?access_token?access_token=85221cc0-9837-45b9-bb72-29e7af104de1`
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



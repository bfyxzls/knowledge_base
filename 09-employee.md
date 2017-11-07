## 9.1 扎帐
### 9.1.1 获取扎帐金额
- 功能描述: 获取扎帐金额

- 请求地址: `http://domain/employee/accounting/calAccount?access_token=token`

- 请求动作: `GET`

- 请求示例: `http://localhost:8080/employee/accounting/calAccount?access_token=85221cc0-9837-45b9-bb72-29e7af104de1`

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
### 9.1.2 生成扎帐支付宝支付二维码信息

- 功能描述: 生成扎帐支付二维码信息


- 请求地址: `http://domain/employee/accounting/generateAlipayQRCode`
- 请求动作: `POST`
- 请求示例: `http://domain/employee/accounting/generateAlipayQRCode?access_token=token&posSn=111`
- 返回示例
```$xslt
{
    "status": "SUCCESS",
    "data": "http://xx"
}
```

### 9.1.3 生成扎帐微信支付二维码信息

- 功能描述: 生成扎帐支付二维码信息


- 请求地址: `http://domain/employee/accounting/generateWeChatQRCode?access_token=token`
- 请求动作: `POST`
- 请求示例: `http://domain/employee/accounting/generateWeChatQRCode?access_token=token&posSn=111&ip=192.168.1.177`
- 返回示例
```$xslt
{
    "status": "SUCCESS",
    "data": "weixin://wxpay/bizpayurl?pr=d1Rn0zD"
}
```

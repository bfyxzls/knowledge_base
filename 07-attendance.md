## 7.1 收费员签到签退信息访问接口AttendanceRecordController
### 7.1.1 save()接口
- 功能描述: 新增收费员签到或签退记录
- 请求地址: `http://domain/attendance/attendanceRecords?access_token=token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/attendance/attendanceRecords?access_token=85221cc0-9837-45b9-bb72-29e7af104de1`
- 请求实体：PS:除了checkTime，其余的属性都需要前台传过来
```$xslt
{
	"district":"蜀山区",
	 "posSn": "123",
     "status": 1,
     "employee":{
     	"id":1002,
     	"name":"赵朋飞",
     	"username":"000039",
        "phoneNum":"18621061900",
        "defaultPost":{
        	"id":1014,
        	"name":"岗位1",
        	"roadSection":{
        		"id":1021,
        		"name":"岳西路-长江西路"
        	}
        }
     }
}
```

- 返回示例
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "id": "AV3tlw6c_Htmjsu8j-q9",
        "employee": {
            "id": 1002,
            "name": "赵朋飞",
            "username": "000039",
            "phoneNum": "18621061900",
            "defaultPost": {
                "id": 1014,
                "name": "岗位1",
                "roadSection": {
                    "id": 1021,
                    "name": "岳西路-长江西路"
                }
            }
        },
        "district": "蜀山区",
        "posSn": "123",
        "checkTime": 1502929712590,
        "status": 1
    }
}
```
### 7.1.2 query()接口
 功能描述: 查询收费员签到签出记录
- 请求地址: `http://domain/attendance/attendanceRecords/query?access_token=token`
- 请求动作: `Get`
- 请求示例: `http://localhost:8080/attendance/attendanceRecords/query?access_token=b3f332ee-c61d-4837-8465-996158f21319&name=赵朋飞&status=2&district=蜀山区&roadSetcionName=潜山路-怀宁路&postName=岗位3&checkTimeRange.startDate=2017-8-15&checkTimeRange.endDate=2017-9-16`
           ps：查询属性可以缺省
- 返回示例
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": "AV3tmC3V_Htmjsu8j-q-",
                "employee": {
                    "id": 1002,
                    "name": "赵朋飞",
                    "username": "000039",
                    "phoneNum": "18621061900",
                    "defaultPost": {
                        "id": 1014,
                        "name": "岗位1",
                        "roadSection": {
                            "id": 1021,
                            "name": "岳西路-长江西路"
                        }
                    }
                },
                "district": "蜀山区",
                "posSn": "123",
                "checkTime": 1502929786119,
                "status": 2
            },
            {
                "id": "AV4eLyr-_Htmjsu8j-sh",
                "employee": {
                    "id": 1002,
                    "name": "赵朋飞",
                    "username": "000039",
                    "phoneNum": "18621061900",
                    "defaultPost": {
                        "id": 1014,
                        "name": "岗位1",
                        "roadSection": {
                            "id": 1021,
                            "name": "岳西路-长江西路"
                        }
                    }
                },
                "district": "蜀山区",
                "posSn": "123",
                "checkTime": 1503744995219,
                "status": 2
            },
            {
                "id": "AV4nHT8Z_Htmjsu8j-sx",
                "employee": {
                    "id": 1002,
                    "name": "赵朋飞",
                    "username": "000039",
                    "phoneNum": "18621061900",
                    "defaultPost": {
                        "id": 1014,
                        "name": "岗位1",
                        "roadSection": {
                            "id": 1021,
                            "name": "岳西路-长江西路"
                        }
                    }
                },
                "district": "蜀山区",
                "posSn": "123",
                "checkTime": 1503894817691,
                "status": 2
            }
        ],
        "facets": [],
        "aggregations": {
            "asMap": {}
        },
        "totalElements": 3,
        "totalPages": 1,
        "size": 20,
        "number": 0,
        "sort": null,
        "first": true,
        "last": true,
        "numberOfElements": 3
    }
}
```


### 7.1.3 queryEmployeeAttendanceByPost接口
- 功能描述: 获取指定岗位下员工当天签到信息
- 请求地址: `http://domain/attendance/attendanceRecords/queryEmployeeAttendanceByPostId?PostId&access_token`
- 请求动作: `Get`
- 请求示例: `http://localhost:8080/attendance/attendanceRecords/queryEmployeeAttendanceByPostId?postId=1021&access_token`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1003,
            "name": "赵朋飞",
            "postName": "岗位3",
            "phoneNum": null,
            "username":"000853",
            "checkStatus": 2,
            "checkTime": null
        },
        {
            "id": 1006,
            "name": "小V",
            "postName": "岗位3",
            "phoneNum": null,
            "checkStatus": 2,
            "checkTime": null
        },
        {
            "id": 1004,
            "name": "刘鹏飞",
            "postName": "岗位3",
            "phoneNum": null,
            "checkStatus": 2,
            "checkTime": null
        },
        {
            "id": 1009,
            "name": "佘能斌",
            "postName": "岗位3",
            "phoneNum": "",
            "checkStatus": 2,
            "checkTime": null
        }
    ]
}
```

### 7.1.4 queryEmployeesAttendanceByRoadSection接口
- 功能描述: 获取指定路段下员工当天签到信息
- 请求地址: `http://domain/attendance/attendanceRecords/queryEmployeesAttendanceByRoadSection?roadSectionId&access_token`
- 请求动作: `Get`
- 请求示例: `http://localhost:8080/attendance/attendanceRecords/queryEmployeesAttendanceByRoadSection?roadSectionId=1020&access_token`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1003,
            "name": "赵朋飞",
            "postName": "岗位3",
            "phoneNum": null,
            "checkStatus": 2,
            "checkTime": null
        },
        {
            "id": 1006,
            "name": "小V",
            "postName": "岗位3",
            "phoneNum": null,
            "checkStatus": 2,
            "checkTime": null
        },
        {
            "id": 1004,
            "name": "刘鹏飞",
            "postName": "岗位3",
            "phoneNum": null,
            "checkStatus": 2,
            "checkTime": null
        },
        {
            "id": 1009,
            "name": "佘能斌",
            "postName": "岗位3",
            "phoneNum": "",
            "checkStatus": 2,
            "checkTime": null
        }
    ]
}
```

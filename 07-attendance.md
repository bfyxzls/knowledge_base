## 7.1 收费员签到签退信息访问接口AttendanceRecordController
### 7.1.1 save()接口
- 功能描述: 新增收费员签到或签退记录
- 请求地址: `http://domain/employee/attendanceRecords?access_token=token`
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
     },
     "coordinate":{
           "type":"Point",
           "coordinates":[
            25,
            16
           ]
          }

}
```

- 返回示例
```$xslt
{
    "status": "SUCCESS"
}
```
### 7.1.2 query()接口
 功能描述: 查询收费员签到签出记录
- 请求地址: `http://domain/employee/attendanceRecords/query?access_token=token`
- 请求动作: `Get`
- 请求示例: `http://localhost:8080/employee/attendanceRecords/query?access_token=b3f332ee-c61d-4837-8465-996158f21319&name=赵朋飞&status=2&district=蜀山区&roadSetcionName=潜山路-怀宁路&postName=岗位3&startDate=2017-8-15&endDate=2017-9-16&id=1003&phoneNum=111111`
           ps：查询属性可以缺省
- 返回示例
```$xslt
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": "5a614fb8bb5b9045b8045b73",
                "name": "张齐健",
                "employeeId": 1003,
                "username":"000858",
                "phoneNum": "15555471960",
                "checkDate": "2018-01-19",
                "checkInTime": "09:54:00",
                "checkInCoordinate": {
                    "type": "Point",
                    "coordinates": [
                        25,
                        16
                    ]
                },
                "checkOutTime": "09:54:07",
                "checkOutCoordinate": {
                    "type": "Point",
                    "coordinates": [
                        25,
                        16
                    ]
                }
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
            "paged": true,
            "unpaged": false
        },
        "totalElements": 1,
        "last": true,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": {
            "sorted": false,
            "unsorted": true
        },
        "numberOfElements": 1,
        "first": true
    }
}
```


### 7.1.3 queryEmployeeAttendanceByPost接口
- 功能描述: 获取指定岗位下员工当天签到信息
- 请求地址: `http://domain/employee/attendanceRecords/queryEmployeeAttendanceByPostId?PostId&access_token`
- 请求动作: `Get`
- 请求示例: `http://localhost:8080/employee/attendanceRecords/queryEmployeeAttendanceByPostId?postId=1021&access_token`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1002,
            "name": "赵朋飞",
            "postName": "岗位1",
            "username": "000039",
            "phoneNum": "18621061900",
            "checkDate": "2018-01-19",
            "checkInTime": "08:35:42",
            "checkInCoordinate": {
                "type": "Point",
                "coordinates": [
                    35,
                    36
                ]
            },
            "checkOutTime": "09:07:56",
            "checkOutCoordinate": {
                "type": "Point",
                "coordinates": [
                    25,
                    16
                ]
            }
        },
        {
            "id": 1003,
            "name": "张齐健",
            "postName": "岗位1",
            "username": "1111148",
            "phoneNum": "15555471960",
            "checkDate": "2018-01-19",
            "checkInTime": "09:54:00",
            "checkInCoordinate": {
                "type": "Point",
                "coordinates": [
                    25,
                    16
                ]
            },
            "checkOutTime": "09:54:07",
            "checkOutCoordinate": {
                "type": "Point",
                "coordinates": [
                    25,
                    16
                ]
            }
        }
    ]
}
```

### 7.1.4 queryEmployeesAttendanceByRoadSection接口
- 功能描述: 获取指定路段下员工当天签到信息
- 请求地址: `http://domain/employee/attendanceRecords/queryEmployeesAttendanceByRoadSection?roadSectionId&access_token`
- 请求动作: `Get`
- 请求示例: `http://localhost:8080/employee/attendanceRecords/queryEmployeesAttendanceByRoadSection?roadSectionId=1020&access_token`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": 1002,
            "name": "赵朋飞",
            "postName": "岗位1",
            "username": "000039",
            "phoneNum": "18621061900",
            "checkDate": "2018-01-19",
            "checkInTime": "08:35:42",
            "checkInCoordinate": {
                "type": "Point",
                "coordinates": [
                    35,
                    36
                ]
            },
            "checkOutTime": "09:07:56",
            "checkOutCoordinate": {
                "type": "Point",
                "coordinates": [
                    25,
                    16
                ]
            }
        },
        {
            "id": 1003,
            "name": "张齐健",
            "postName": "岗位1",
            "username": "1111148",
            "phoneNum": "15555471960",
            "checkDate": "2018-01-19",
            "checkInTime": "09:54:00",
            "checkInCoordinate": {
                "type": "Point",
                "coordinates": [
                    25,
                    16
                ]
            },
            "checkOutTime": "09:54:07",
            "checkOutCoordinate": {
                "type": "Point",
                "coordinates": [
                    25,
                    16
                ]
            }
        }
    ]
}
```

### 7.1.5 queryEmployeeAttendanceById接口
- 功能描述: 获取员工当天签到信息
- 请求地址: `http://domain/employee/attendanceRecords/queryEmployeeAttendanceById?access_token&d=5a613d5ebb5b901f74705977`
- 请求动作: `Get`
- 请求示例: `http://localhost:8080/employee/attendanceRecords/queryEmployeeAttendanceById?id=5a613d5ebb5b901f74705977&access_token`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "id": "5a614fb8bb5b9045b8045b73",
            "name": "张齐健",
            "employeeId": 1003,
            "username":"000858",
            "phoneNum": "15555471960",
            "checkDate": "2018-01-19",
            "checkInTime": "09:54:00",
            "checkInCoordinate": {
                "type": "Point",
                "coordinates": [
                    25,
                    16
                ]
            },
            "checkOutTime": null,
            "checkOutCoordinate": null
        },
        {
            "id": "5a614fb8bb5b9045b8045b73",
            "name": "张齐健",
            "employeeId": 1003,
            "username":"000858",
            "phoneNum": "15555471960",
            "checkDate": "2018-01-19",
            "checkInTime": null,
            "checkInCoordinate": null,
            "checkOutTime": "09:54:07",
            "checkOutCoordinate": {
                "type": "Point",
                "coordinates": [
                    25,
                    16
                ]
            }
        }
    ]
}
```


### 7.1.6 queryMotionTrailById接口
- 功能描述: 获取指定员工当天运动轨迹信息
- 请求地址: `http://domain/employee/attendanceRecords/queryMotionTrailById?access_token&id=5a613d5ebb5b901f74705977`
- 请求动作: `Get`
- 请求示例: `http://localhost:8080/employee/attendanceRecords/queryMotionTrailById?id=5a613d5ebb5b901f74705977&access_token`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": [
        {
            "checkTime": "2018-01-19 08:35:42",
            "checkCoordinate": {
                "type": "Point",
                "coordinates": [
                    35,
                    36
                ]
            }
        },
        {
            "checkTime": "2018-01-19 09:06:34",
            "checkCoordinate": {
                "type": "Point",
                "coordinates": [
                    35,
                    36
                ]
            }
        },
        {
            "checkTime": "2018-01-19 09:07:36",
            "checkCoordinate": {
                "type": "Point",
                "coordinates": [
                    25,
                    16
                ]
            }
        },
        {
            "checkTime": "2018-01-19 09:07:56",
            "checkCoordinate": {
                "type": "Point",
                "coordinates": [
                    25,
                    16
                ]
            }
        }
    ]
}
```

### 7.1.7 uploadMotionTrail接口
- 功能描述: 上传运动轨迹
- 请求地址: `http://domain/employee/attendanceRecords/uploadMotionTrail?access_token=token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/attendance/attendanceRecords/uploadMotionTrail?access_token=85221cc0-9837-45b9-bb72-29e7af104de1`
- 请求实体：PS:除了checkTime，其余的属性都需要前台传过来
```$xslt
{
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
     },
     "coordinate":{
           "type":"Point",
           "coordinates":[
            25,
            16
           ]
          }

}
```

- 返回示例
```$xslt
{
    "status": "SUCCESS",
    "data": "上传位置成功"
}
```

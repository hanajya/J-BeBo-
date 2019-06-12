# 16.排课管理模块
## 16.1.排课列表 {#schedule-list}
### 请求路径
`GET /schedule/list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|N|排课编号|
|status|body|int|N|课程状态 10 未开始 20进行中 30 已结束|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|code|body|string|Y|排课code|
|coachCode|body|string|Y|教练code|
|createdAt|body|int|Y|排课时间|
|fieldName|body|string|Y| 场地名|
|fieldImage|body|string|Y| 场地图|
|phone|body|string|Y| 场地电话|
|remark|body|string|Y|备注|
|personNum|body|int|Y|学生人数|
|status|body|string|Y|课程状态|
|upperCourseAt|body|date|Y|上课时间|
|coach_name|body|string|Y|教练名|
### 返回示例

```json
{
    "request": "ec07551f-7a16-4e5b-99cd-85ee3ebb138c",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 14,
                "code": "CSM000001",
                "coachCode": "COM000001",
                "upperCourseAt": "2018-12-31 10:00:00",
                "fieldName": "篮球",
                "fieldImage": "https://www.baidu.com",
                "phone": "18665736316",
                "categoryCode": "CTM000001",
                "province": "海南",
                "city": "三亚",
                "district": "南滨",
                "address": "红光山顶",
                "personNum": 2,
                "remark": "",
                "merchantCode": "M000002",
                "status": 10,
                "createdAt": "2018-12-31 14:32:02",
                "updatedAt": "2018-12-31 15:56:02"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 16.2.学员详情列表 {#schedule-student-list}
### 请求路径
`GET /schedule/student-list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|用户编码|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|name|body|string|Y|学员姓名|
|phone|body|string|Y|手机号码|
|usercourse.levelName|body|string|Y|课程级别|
|usercourse.title|body|string|Y|课程名称|
|usercourse.courseSection|body|array|Y|用户课程节数|
|usercourse.courseSection.status|body|int|Y|0未开始 10已上课 20 出席 30 请假 40旷课 50 到场|
|usercourse.courseSection.code|body|string|Y|用户课程节code|
### 返回示例

```json
{
    "request": "4b0e2881-9f9f-418e-bb54-754fbc6ec0eb",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        {
            "name": "篮球1",
            "phone": "18665736315",
            "code": "UM000001",
            "usercourse": [
                {
                    "id": 1,
                    "code": "UC000001",
                    "title": "PDS蓝球",
                    "image": "2.jpg",
                    "label": [
                        "龙大人",
                        "lsls"
                    ],
                    "type": 20,
                    "totalSection": 9,
                    "useSection": 0,
                    "categoryCode": "CTM000001",
                    "status": 10,
                    "userCode": "UM000001",
                    "merchantCode": "M000002",
                    "fieldCode": "FDM000001",
                    "orderCode": "OM000001",
                    "courseCode": "COR000001",
                    "createdAt": "2018-12-29 10:45:35",
                    "updatedAt": "2018-12-29 10:45:35",
                    "fieldName": "篮球",
                    "levelName": "",
                    "courseSection": [
                        {
                            "id": 20,
                            "code": "UCS000001",
                            "status": 0,
                            "type": 20,
                            "coachName": "篮球1",
                            "upperCourseAt": "2018-12-31 10:00:00",
                            "place": "海南三亚南滨红光山顶"
                        },
                        {
                            "id": 21,
                            "code": "UCS000002",
                            "status": 0,
                            "type": 20,
                            "coachName": "",
                            "upperCourseAt": "",
                            "place": ""
                        },
                        {
                            "id": 22,
                            "code": "UCS000003",
                            "status": 0,
                            "type": 20,
                            "coachName": "",
                            "upperCourseAt": "",
                            "place": ""
                        },
                        {
                            "id": 23,
                            "code": "UCS000004",
                            "status": 0,
                            "type": 20,
                            "coachName": "",
                            "upperCourseAt": "",
                            "place": ""
                        },
                        {
                            "id": 24,
                            "code": "UCS000005",
                            "status": 0,
                            "type": 20,
                            "coachName": "",
                            "upperCourseAt": "",
                            "place": ""
                        },
                        {
                            "id": 25,
                            "code": "UCS000006",
                            "status": 0,
                            "type": 20,
                            "coachName": "",
                            "upperCourseAt": "",
                            "place": ""
                        },
                        {
                            "id": 26,
                            "code": "UCS000007",
                            "status": 0,
                            "type": 20,
                            "coachName": "",
                            "upperCourseAt": "",
                            "place": ""
                        },
                        {
                            "id": 27,
                            "code": "UCS000008",
                            "status": 0,
                            "type": 20,
                            "coachName": "",
                            "upperCourseAt": "",
                            "place": ""
                        }
                    ]
                }
            ]
        }
    ]
}
```

## 16.5.学员列表-操作 {#schedule-modify-status}
### 请求路径
`POST /schedule/modify-status`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|用户课程节code 地址栏携带|
|status|body|string|Y|0未开始 10已上课 20 出席 30 请假 40旷课 50 到场|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "3b3af1fa-c617-434c-a53b-476572988db9",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        1
    ]
}
```


## 16.6.上课图片/视频 {#schedule-imageorvideo}
### 请求路径
`GET /schedule/imageorvideo`
### 请求参数
无
### 请求示例
无
### 返回参数
无
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|int|Y|用户课程节数code|
|type|body|int|Y|课程类型|
|contentType|body|int|Y|内容类型 10图片 20 视频|
|content|body|int|Y|内容|
### 返回示例

```json
{
    "request": "c6df4975-54a2-4dd2-b80a-236d78c77a57",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```



## 16.7.学员排课操作 {#schedule-create}
### 请求路径
`POST /schedule/create`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|category_code|body|string|Y|分类code|
|field_code|body|string|N|场地code|
|coach_code|body|string|N|教练code|
|user_code|body|array|N|学员code|
|upper_course_at|body|date|N|上课时间|
|province|body|string|N|省|
|city|body|string|N|市|
|district|body|string|N|区|
### 请求示例
```
	"upper_course_at":"2018-12-31 10:00:00",
	"coach_code":"COM000001",
	"user_code":["UM000001","UM000002"]
```
### 返回参数
无
### 返回示例

```json
{
    "request": "0cffc525-967c-477a-9a25-dfdc41744823",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 16.8.学员排课操作--编辑排课 {#schedule-modify}
### 请求路径
`POST /schedule/modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|排课编码 地址栏携带|
|field_code|body|string|N|场地code|
|coach_code|body|int|N|教练code|
|upper_course_at|body|date|N|上课时间|
|province|body|string|N|省|
|city|body|string|N|市|
|district|body|string|N|区|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "0cffc525-967c-477a-9a25-dfdc41744823",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 16.9.选择用户 {#schedule-choose-user}
### 请求路径
`GET /schedule/choose-user`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|category_code|body|string|Y|分类code|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "e8ff26e5-44e2-40c5-8176-01c8606442c9",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        {
            "userCourseCode": "UC000001",
            "user": {
                "code": "UM000001",
                "nickname": "龙大人1",
                "name": "篮球1"
            }
        },
        {
            "userCourseCode": "UC000002",
            "user": {
                "code": "UM000002",
                "nickname": "龙大人1",
                "name": "篮球1"
            }
        }
    ]
}
```

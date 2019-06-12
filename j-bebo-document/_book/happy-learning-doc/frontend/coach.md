#4.教练模块
## 4.1.获取学员信息 {#coach-login}
### 请求路径
`POST /coach-login`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|phone|body|string|Y|手机号|
|pwd|body|string|Y|密码|
### 请求示例
无
### 返回参数
无

### 返回示例
```json
{
    "request": "159c33d1-b897-454b-b3bd-c6fed49d203e",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 4,
        "code": "COM000001",
        "merchantCode": "M000009",
        "username": "zzz",
        "password": "$2y$10$RUpakKoJOxzt3M8GVb4YFOJJR5J5DnrTde70ipG5KM.RngKyh/Jyq",
        "avatar": "",
        "name": "篮球1",
        "sex": "",
        "age": "",
        "phone": "18665736315",
        "expertise": [
            "music",
            "movie",
            "idol"
        ],
        "status": 10,
        "createdAt": "2019-01-04 10:22:27",
        "updatedAt": "2019-01-04 10:22:27"
    }
}
```



## 4.2.教练资料修改 {#coach-modify}
### 请求路径
`POST /coach-modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|avatar|body|string|N|头像|
|username|body|string|N|用户名|
|sex|body|int|N|性别 10未知 20男 30女|
|age|body|int|N|年龄|
|expertise|body|array|N|专长|
### 请求示例
无
### 返回参数
无

### 返回示例
```json
{
    "request": "e3c0475d-3206-4bf0-a99b-9367f96f36a1",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```



## 4.3.我的课程 {#coach-mycouser}
### 请求路径
`GET /coach-mycouser`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|教练code|
|createdAt|body|int|Y|排课时间|
|status|body|int|Y| 状态 10 未开始 20 进行中 30 已结束|
|upperCourseAt|body|int|Y| 上课时间|
|code|body|int|string| 排课code|
|personNum|body|string|Y| 人数|
|remark|body|string|Y| 备注|
|remark|body|string|Y|备注|
### 返回示例

```json
{
    "request": "cdb35f3f-c35b-4b39-a5de-5a7754232aac",
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


## 4.4.我的课程详情 {#coach-coursedetail}
### 请求路径
`GET /coach-coursedetail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|class_scheduling_code|body|string|Y|排课code|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|createdAt|body|int|Y|排课时间|
|status|body|int|Y| 状态 10 未开始 20 进行中 30 已结束|
|upperCourseAt|body|int|Y| 上课时间|
|personNum|body|string|Y| 人数|
|remark|body|string|Y|备注|
|code|body|string|Y|用户课程节数编码|
|user.userCode|body|string|Y|学员id|
|user.avatar|body|string|Y|学员头像|
|user.nickname|body|string|Y|学员昵称|
|user.phone|body|string|Y|学员电话|
|user.status|body|array|Y|学员状态 10已上课 20 出席 30 请假 40旷课 50 到场|

### 返回示例

```json
{
    "request": "77742227-7dd8-4c2d-87b8-31e76cc2bf34",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "header": {
            "upperCourseAt": "2018-12-31 10:00:00",
            "remark": null,
            "address": "红光山顶",
            "province": "海南",
            "city": "三亚",
            "district": "南滨",
            "status": 10,
            "personNum": 2
        },
        "footer": {
            "data": [
                {
                    "id": 20,
                    "code": "UCS000001",
                    "userCode": "UM000001",
                    "status": 20,
                    "type": 20,
                    "user": {
                        "id": 1,
                        "code": "UM000001",
                        "merchantCode": "M000009",
                        "avatar": "",
                        "nickname": "龙大人1",
                        "sex": "",
                        "age": "",
                        "height": "",
                        "phone": "18665736316",
                        "parentName": "",
                        "parentPhone": "",
                        "parentWechat": "",
                        "relationship": 1,
                        "name": "篮球1",
                        "touchTime": 10,
                        "createdAt": "2019-01-02 18:33:00",
                        "updatedAt": "2019-01-02 18:33:00"
                    }
                }
            ],
            "currentPage": 1,
            "total": 1,
            "perPage": "10",
            "lastPage": 1
        }
    }
}
```


## 4.5.学员点名 {#coach-rollcall}
### 请求路径
`POST /coach-rollcall`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|用户课程节 编码|
|status|body|int|Y|出席状态|
### 请求示例
无
### 返回参数
无

### 返回示例
```json
{
    "request": "a16809d5-89d7-4604-838d-df957fb0e336",
    "code": 0,
    "message": "request_handle_successful",
    "data": "状态更改成功"
}
```


## 4.8.资料上传 {#coach-upload}
### 请求路径
`POST /coach-upload`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|user_course_code|body|string|Y|用户课程节编码|
|type|body|int|Y|课程类型 10正式 20体验|
|ctype|body|int|Y|上传类型 10图片 20视频|
|content|body|int|N|内容|
|files|body|array|N| 上传的图片或视频|
### 请求示例
无
### 返回参数
无

### 返回示例

```json
{
    "request": "881cb174-8544-404f-a6ad-aaf6d3cbc08c",
    "code": 0,
    "message": "request_handle_successful",
    "data": "上传成功"
}
```


## 4.9.我的消息 {#coach-mymessage}
### 请求路径
`GET /coach-mymessage`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|classSchduleingCode|body|int|Y|排课编号|
|sectionId|body|array|Y|第几节|
|userCourse.title|body|string|Y|课程名|
|userCourse.classSchdule.status|body|int|Y|10 进行中 20已结束|

### 返回示例
```json
{
    "request": "2763b6da-601c-4310-8195-d62def211a30",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 1,
                "merchantCode": "M00000B",
                "coachCode": "COM000001",
                "classSchduleingCode": "CSM000001",
                "status": 0,
                "createdAt": "2019-01-06 13:04:18",
                "updatedAt": "2019-01-06 13:06:23",
                "code": "UCS000001",
                "userCourseCode": "UC000001",
                "upperCourseAt": "2018-12-31 10:00:00",
                "place": "海南三亚南滨红光山顶",
                "coachName": "篮球1",
                "coachPhone": "18665736315",
                "classSchedulingCode": "CSM000001",
                "userCode": "UM000001",
                "sectionId": "1",
                "type": 20,
                "userCourse": [
                    {
                        "title": "PDS蓝球ed",
                        "fieldName": "",
                        "levelName": "",
                        "courseSection": [],
                        "pivot": {
                            "classSchedulingCode": "CSM000001",
                            "userCourseCode": "UC000001"
                        }
                    }
                ],
                "classSchdule": {
                    "status": 10,
                    "code": "CSM000001"
                }
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```

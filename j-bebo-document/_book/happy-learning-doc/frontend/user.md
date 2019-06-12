#3.用户模块

## 3.1.学员资料修改 {#user-modify}
### 请求路径
`POST /api/user-modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|avatar|body|string|N|头像|
|nickname|body|string|N|昵称|
|sex|body|int|N|性别|
|height|body|int|N|身高|
|age|body|int|N|年龄|
|parent_name|body|string|N|家长名称|
|parent_phone|body|int|N|家长手机|
|parent_wechat|body|string|N|家长微信|
|relationship|body|int|N|关系 10父子 20父女 30母子 40母女|
### 请求示例
无
### 返回参数
无
### 返回示例
```json

```

##3.2.获取学员信息 {#user-getuserinfo}
### 请求路径
`GET /api/user-getuserinfo`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|user_code|body|string|N|不传 则是学员，传则是教练查看|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|id|
|avatar|body|string|Y|头像|
|nickname|body|string|Y|昵称|
|phone|body|string|Y|手机号|
	.
	.
	.
### 返回示例
```json

```


## 3.3 我的课程订单 {#user-mycourseorder}
### 请求路径
`GET /api/user-mycourseorder`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|order_status|body|int|Y|订单状态 10 全部 20待付款 30已付款 40预约订单|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|订单id|
|created_at|body|int|Y|下单时间|
|order_status|body|int|Y|订单状态|
|course_image|body|string|Y|图片|
|level_name|body|string|Y|级别名称|
|stage_num|body|int|Y|期数|
|give_num|body|int|Y|赠送节数|
|type|body|int|Y|课程类型|
|course_name|body|string|Y|课程名|
|price|body|decimal|Y|课程每期定价|
|stage_section|body|int|Y|每期节数|
|stage_amont|body|decimal|Y|课程金额|

### 返回示例
```json

```


## 3.4 订单详情 {#user-orderdetail}
### 请求路径
`GET /api/user-orderdetail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|订单code|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|singleUser.avatar|body|string|Y|头像|
|singleUser.nickname|body|string|Y|昵称|
|singleUser.phone|body|string|Y|手机号|
|field_name|body|string|Y|场地名|
|address|body|string|Y|场地位置|
|order_status|body|string|Y|订单状态 10 全部 20待付款 30已付款 40预约订单|
|order_number|body|string|Y|订单编码|
|created_at|body|string|Y|下单时间|
|level_name|body|string|Y|级别名称|
|stage_num|body|int|Y|期数|
|give_num|body|int|Y|赠送节数|
|type|body|int|Y|课程类型|
|course_name|body|int|Y|课程名|
|price|body|int|Y|课程每期定价|
|stage_section|body|int|Y|每期节数|
|stage_amont|body|int|Y|课程金额|

### 返回示例
```json
{
    "request": "978f2196-e588-413e-8372-c944eaa073ca",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 8,
        "code": "OM000001",
        "merchantCode": "M000002",
        "orderNumber": "15460515356987",
        "type": 20,
        "amount": "",
        "payType": 20,
        "fieldName": "篮球",
        "courseImage": "2.jpg",
        "province": "海南",
        "city": "三亚",
        "district": "南滨",
        "address": "红光山顶",
        "subscribeAt": "2018-12-29 10:45:35",
        "price": "",
        "levelName": "",
        "stageNum": "",
        "giveNum": "",
        "courseAmount": "",
        "userCode": "UM000001",
        "createPersonCode": "AM000002",
        "userName": "篮球1",
        "courseName": "PDS蓝球",
        "stageSection": "",
        "orderStatus": 50,
        "coachName": "",
        "coachPhone": "",
        "userPhone": "18665736315",
        "fieldCode": "FDM000001",
        "status": "20",
        "createdAt": "2018-12-29 10:45:35",
        "updatedAt": "2018-12-29 10:45:35",
        "singleUser": {
            "avatar": "",
            "nickname": "龙大人1",
            "code": "UM000001",
            "phone": "18665736316"
        }
    }
}
```


## 3.5.我的课程 {#user-mycourse}
### 请求路径
`GET /api/user-mycourse`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|user_code|body|int|N|学员id 为空时，学员自己查看，不为空时，教练查看|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|课程id|
|created_at|body|int|Y|购买时间|
|status|body|int|Y|状态 10未开始 20 进行中 30 已结束|
|title|body|string|Y|课程名称|
|image|body|string|Y|图片|
|type|body|int|Y|课程类型 10 正式 20 体验 type为20时，created_at为预约时间|
|place|body|string|Y|场地名称|
|totalSection|body|int|Y|总节数|
|useSection|body|int|Y|已上节数|

### 返回示例
```json
{
    "request": "cc632be4-2740-4ffc-82ae-1374ee347e17",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 1,
                "code": "UC000001",
                "title": "PDS蓝球",
                "image": "2.jpg",
                "type": 20,
                "totalSection": 9,
                "useSection": 0,
                "categoryCode": "CTM000001",
                "status": 10,
                "userCode": "UM000001",
                "merchantCode": "M000009",
                "fieldCode": "FDM000001",
                "orderCode": "OM000001",
                "courseCode": "COR000001",
                "createdAt": "2018-12-29 10:45:35",
                "updatedAt": "2018-12-29 10:45:35",
                "fieldName": "篮球",
                "levelName": ""
            },
            {
                "id": 2,
                "code": "UC000002",
                "title": "PDS蓝球",
                "image": "2.jpg",
                "type": 20,
                "totalSection": 9,
                "useSection": 0,
                "categoryCode": "CTM000001",
                "status": 10,
                "userCode": "UM000002",
                "merchantCode": "M000009",
                "fieldCode": "FDM000001",
                "orderCode": "OM000002",
                "courseCode": "COR000001",
                "createdAt": "2018-12-31 11:48:42",
                "updatedAt": "2018-12-31 11:48:42",
                "fieldName": "篮球",
                "levelName": ""
            }
        ],
        "currentPage": 1,
        "total": 2,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 3.6.我的课程详情 {#user-coursedetail}
### 请求路径
`GET /api/user-coursedetail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|int|Y|用户课程编码|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|created_at|body|int|Y|购买时间|
|status|body|int|Y|整个课程状态 10未开始 20 进行中 30 已结束|
|title|body|string|Y|课程名称|
|label|body|array|Y|标签|
|section_name|body|string|Y|课程第几节|
|courseSection.upperCourseAt|body|int|Y|上课时间|
|courseSection.place|body|int|Y|上课地点|
|courseSection.coachName|body|string|Y|上课教练|
|courseSection.status|body|int|Y|状态 10已上课 20 出席 30 请假 40旷课 50 到场|

### 返回示例
```json
{
    "request": "a95dabe7-a0ba-4795-a5fc-eaa8e0468fba",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
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
            "merchantCode": "M000009",
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
                    "status": 10,
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
```


## 3.7.我的消息 {#user-mymessage}
### 请求路径
`GET /api/user-mymessage`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|userCourse.title|body|string|Y|课程名称|
|section_id|body|int|Y|课程节数id|
|userCourse.status|body|int|Y|课程状态 10 进行中 20已结束|

### 返回示例
```json

```


## 3.8.查看课程第几节的上课资料 {#user-sectioninfo}
### 请求路径
`GET /api/user-sectioninfo`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|课程节数编码|
|ucode|body|string|Y|用户课程编码|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|createdAt|body|int|Y|购买时间|
|status|body|int|Y|10未开始 20 进行中 30 已结束|
|title|body|string|Y|课程名称|
|image|body|string|Y|图片|
|type|body|int|Y|10 正式 20体验|
|upper_course_at|body|int|Y|上课时间|
|place|body|string|Y|上课地点|
|type|body|int|Y|类型 10正式 20体验|
|content_type|body|int|Y|资料类型 10图片 20视频|
|images|body|string|Y|图片 content_type = 10|
|videos|body|string|Y|视频 content_type = 20|
|is_coach|body|int|Y|当前查看人 是否是教练  1是教练 0不是教练 (暂缺)|

### 返回示例
```json
{
    "request": "b3108fbe-3790-4518-929e-1584defe15ae",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "label": [
            "龙大人",
            "lsls"
        ],
        "title": "PDS蓝球",
        "image": "2.jpg",
        "fieldName": "",
        "levelName": "",
        "courseSection": [],
        "footer": [
            {
                "id": 20,
                "code": "UCS000001",
                "userCourseCode": "UC000001",
                "upperCourseAt": "2018-12-31 10:00:00",
                "place": "海南三亚南滨红光山顶",
                "coachName": "篮球1",
                "coachPhone": "18665736315",
                "classSchedulingCode": "CSM000001",
                "userCode": "UM000001",
                "status": 10,
                "merchantCode": "M000009",
                "type": 20,
                "createdAt": "2018-12-29 10:45:35",
                "updatedAt": "2018-12-31 17:47:49",
                "userCourseSectionInfo": [
                    {
                        "id": 1,
                        "userCourseSectionCode": "UCS000001",
                        "type": 1,
                        "contentType": 2,
                        "content": "dddd",
                        "createdAt": "",
                        "updatedAt": ""
                    }
                ]
            }
        ]
    }
}
```


## 3.9.我的消费 {#user-mypayment}
### 请求路径
`GET /api/user-mypayment`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|total|body|decimal|Y|总金额|
|orderNumber|body|string|Y|订单号|
|payTime|body|int|Y|支付时间|
|payMoney|body|decimal|Y|支付金额|

### 返回示例
```json

```


## 3.10.关于我们 {#user-aboutus}
### 请求路径
`GET /api/user-aboutus`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|logo|body|string|Y|logo图|
|companyName|body|string|Y|公司名称|
|customServiceMobile|body|string|Y|客服电话|
|desc|body|string|Y|简介|

### 返回示例
```json
{
    "request": "dae1da30-7558-4f28-8e29-c8ffe8b4055e",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 1,
        "merchantCode": "M00000B",
        "companyLogo": "www.hdl",
        "companyName": "龙歌歌",
        "desc": "漫山遍野",
        "customServiceMobile": "18665736315",
        "createdAt": "2019-01-06 14:26:31",
        "updatedAt": "2019-01-06 14:26:31"
    }
}
```
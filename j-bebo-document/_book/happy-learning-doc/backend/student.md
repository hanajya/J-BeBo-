# 15.学员管理模块
## 15.1.学员列表 {#user-list}
### 请求路径
`GET /user/list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|name|body|string|N|姓名|
|phone|body|string|N|手机|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|avatar|body|string|Y|头像|
|nickname|body|string|Y|昵称|
|name|body|string|Y|姓名|
|height|body|int|Y|身高|
|sex|body|int|Y|性别 10未知 20男 30女|
|age|body|int|Y|年龄|
|phone|body|string|Y|手机号|
|parentName|body|string|Y|家长姓名|
|parentPhone|body|string|Y|家长手机号|
|parentWechat|body|string|Y|家长微信号|
|relationship|body|string|Y|关系 |
|createdAt|body|int|Y|创建时间|
### 返回示例

```json
{
    "request": "c15759c2-1821-4fe6-9d19-1aa9c54c89cd",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 1,
                "code": "UM000001",
                "merchantCode": "M000002",
                "avatar": "",
                "nickname": "龙大人1",
                "sex": "",
                "age": "",
                "height": "",
                "phone": "18665736315",
                "parentName": "",
                "parentPhone": "",
                "parentWechat": "",
                "relationship": 1,
                "name": "篮球1",
                "createdAt": "2018-12-27 18:17:59",
                "updatedAt": "2018-12-27 18:40:44"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 15.2.新增学员 {#user-create}
### 请求路径
`POST /user/create`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|avatar|body|string|N|头像|
|nickname|body|string|N|昵称|
|name|body|string|N|姓名|
|height|body|int|N|身高|
|sex|body|int|Y|性别 10未知 20男 30女|
|age|body|int|N|年龄|
|phone|body|string|Y|手机号|
|parent_name|body|string|N|家长姓名|
|parent_phone|body|string|N|家长手机号|
|parent_wechat|body|string|N|家长微信号|
|relationship|body|string|N|关系|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "c7148927-7dd0-424d-abbb-31097505e541",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 15.3.编辑学员 {#user-modify}
### 请求路径
`POST /user/modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|avatar|body|string|N|头像|
|nickname|body|string|N|昵称|
|name|body|string|N|姓名|
|height|body|int|N|身高|
|sex|body|int|N|性别 10未知 20男 30女|
|age|body|int|N|年龄|
|phone|body|string|N|手机号|
|parent_name|body|string|N|家长姓名|
|parent_phone|body|string|N|家长手机号|
|parent_wechat|body|string|N|家长微信号|
|relationship|body|string|N|关系|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "1c929a73-acf4-48f2-a4e2-58290bb361fe",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```



## 15.4.删除学员 {#user-delete}
### 请求路径
`POST /user/delete`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|用户编码 地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "90677951-0603-4272-8e4e-2a84c17a535f",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```





## 15.5.学员课程列表--课程信息概览 {#user-course-list}
### 请求路径
`GET /user/course-list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|status|body|int|N|10 未开始 20 进行中 30 已结束|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|code|body|string|Y|编码|
|createdAt|body|int|Y|购买时间|
|status|body|int|Y|课程状态 10 未开始 20 进行中 30 已结束|
|title|body|string|Y|课程名|
|levelName|body|string|Y|级别名 type = 20为体验课程 无级别|
|fieldName|body|string|Y|场地名|
|totalSection|body|string|Y|总计节数|
|useSection|body|string|Y|已上课节数|
|balanceSection|body|string|Y|剩余节数 自己算哈|
### 返回示例

```json
{
    "request": "87da996c-628b-4e5d-8779-03fc850bd4b3",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
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
                "merchantCode": "M000002",
                "fieldCode": "FDM000001",
                "orderCode": "OM000001",
                "courseCode": "COR000001",
                "createdAt": "2018-12-29 10:45:35",
                "updatedAt": "2018-12-29 10:45:35",
                "fieldName": "篮球",
                "levelName": ""
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 15.6.学员课程列表--课程表(上课信息) {#user-course-info}
### 请求路径
`GET /user/course-info`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|user_course_code|body|int|用户课程id,列表中获取|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|user_code|body|int|Y|学员id|
|name|body|int|Y|学员姓名|
|diffTimes.nodistributeTimes|body|int|Y|未分配次数|
|diffTimes.attendTimes|int|Y|出席次数|
|diffTimes.upclassTimes|int|Y|已上课次数|
|diffTimes.leaveTimes|int|Y|请假次数|
|diffTimes.cutTimes|int|Y|旷课次数|
|courseSection.code|int|Y|课程节数编码|
|courseSection.status|int|Y|课程节数状态|
|courseSection.type|int|Y|课程类型|
|courseSection.coachName|string|Y|教练名称|
|courseSection.upperCourseAt|int|Y|上课时间|
|courseSection.place|string|Y|上课地点|
### 返回示例

```json
{
    "request": "3a00e39d-a955-4000-8bc5-8911f37b875d",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "code": "UC000001",
        "type": 20,
        "title": "PDS蓝球",
        "diffTimes": {
            "nodistributeTimes": 9,
            "upclassTimes": 0,
            "attendTimes": 0,
            "leaveTimes": 0,
            "cutTimes": 0
        },
        "fieldName": "",
        "levelName": "",
        "courseSection": [
            {
                "id": 20,
                "code": "UCS000001",
                "status": 0,
                "type": 20,
                "coachName": "",
                "upperCourseAt": "",
                "place": ""
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
            },
            {
                "id": 28,
                "code": "UCS000009",
                "status": 0,
                "type": 20,
                "coachName": "",
                "upperCourseAt": "",
                "place": ""
            }
        ]
    }
}
```

## 15.7.学员详情 {#user-detail}
### 请求路径
`GET /user/detail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|用户编码 地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "549d62ec-d7f7-4b61-b868-041c9d4e25bd",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 2,
        "code": "UM000001",
        "merchantCode": "M000002",
        "avatar": "",
        "nickname": "龙大人1",
        "sex": "",
        "age": "",
        "height": "",
        "phone": "18665736315",
        "parentName": "",
        "parentPhone": "",
        "parentWechat": "",
        "relationship": 1,
        "name": "篮球1",
        "createdAt": "2018-12-27 18:51:11",
        "updatedAt": "2018-12-27 18:51:11"
    }
}
```


## 15.8.总平台学员/学长列表 {#user}
### 请求路径
`GET /user`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|name|body|string|N|姓名|
|phone|body|string|N|手机|
|merchant_code|body|string|N|商户编码|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "7e5e85a1-8c0a-4d78-88fa-9604591f378d",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 2,
                "code": "UM000001",
                "merchantCode": "M000002",
                "avatar": "",
                "nickname": "龙大人1",
                "sex": "",
                "age": "",
                "height": "",
                "phone": "18665736315",
                "parentName": "",
                "parentPhone": "",
                "parentWechat": "",
                "relationship": 1,
                "name": "篮球1",
                "createdAt": "2018-12-27 18:51:11",
                "updatedAt": "2018-12-27 18:51:11"
            },
            {
                "id": 3,
                "code": "UM000002",
                "merchantCode": "M000002",
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
                "createdAt": "2018-12-31 11:44:24",
                "updatedAt": "2018-12-31 11:44:24"
            }
        ],
        "currentPage": 1,
        "total": 2,
        "perPage": "10",
        "lastPage": 1
    }
}
```
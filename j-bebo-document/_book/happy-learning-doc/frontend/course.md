#2.课程模块
## 2.1.课程详情 {#course-detail}
### 请求路径
`GET /api/course-detail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|课程code 地址栏携带|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|课程code|
|title|body|string|Y|标题|
|content|body|string|Y|阶段信息|
|price|body|decimal|Y|每期定价|
|image|body|string|Y|图片链接|
|label|body|array|Y|标签信息|
|section|body|int|Y|每期节数|
|type|body|int|Y|课程类型 10正式 20体验|
|categoryCode|body|string|Y|课程分类code|
|levelStage.risk|body|string|Y|风险提示|
|levelStage.name|body|string|Y|级别名称|
|levelStage.maxStage|body|int|Y|最大期数 自行至最大循环|
|levelStage.stageNum|body|int|Y|购课优惠中的xx期|
|levelStage.giveNum|body|int|Y|购课优惠中的xx节|

### 返回示例
```json
{
    "request": "7567fd36-1503-42db-a1dd-d16d3dcc0edf",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "code": "COR000004",
        "title": "PDS蓝球e",
        "content": "x66xx",
        "price": "100.00",
        "image": "1.jpg",
        "label": [
            "龙大人",
            "lsls"
        ],
        "status": 10,
        "stageCode": "SM000001",
        "type": 20,
        "categoryCode": "CTM000001",
        "section": "8",
        "levelStage": [
            {
                "code": "LM000002",
                "name": "篮球",
                "maxStage": 3,
                "risk": "",
                "stageNum": "1",
                "giveNum": 3
            },
            {
                "code": "LM000003",
                "name": "篮球1",
                "maxStage": 3,
                "risk": "",
                "stageNum": "1",
                "giveNum": 3
            }
        ]
    }
}
```

##2.2.上课场地 {#class-place}
### 请求路径
`GET /api/class-place`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|int|Y|分类code(蓝球/足球...),地址栏携带|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|场地code|
|name|body|string|Y|场地名称|
|image|body|string|Y|场地图片|
|province|body|string|Y|省|
|city|body|string|Y|市|
|district|body|string|Y|区|
|address|body|string|Y|场地位置|

### 返回示例
```json
{
    "request": "30f24c20-f57f-4e02-93d6-e65ee8ae5fb0",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        {
            "name": "篮球1",
            "image": "1.jpg",
            "code": "FDM000002",
            "phone": "18665736315",
            "province": "海南",
            "city": "三亚",
            "district": "南滨",
            "address": "红光山顶"
        }
    ]
}
```


## 2.3.学员报名信息 {#user-show}
### 请求路径
`GET /api/user-show`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|avatar|body|string|Y|头像|
|nickname|body|string|Y|昵称|
|sex|body|string|Y|性别|
|height|body|int|Y|身高|
|age|body|int|Y|年龄|
|phone|body|string|Y|手机号|
|parent_name|body|string|N|家长名|
|parent_phone|body|string|N|家长手机|
|parent_wechat|body|string|N|家长微信|
|relationship|body|int|N|关系 10父子 20父女 30母子 40母女|
|touch_time|body|string|Y|接触时间|
### 返回示例
```json
{
    "request": "277d2511-5056-41c4-bf11-5f14922c6fdf",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 1,
        "code": "UM000001",
        "merchantCode": "M000009",
        "avatar": "",
        "nickname": "龙大人1",
        "sex": 10,
        "age": "",
        "height": "",
        "phone": "18665736315",
        "parentName": "",
        "parentPhone": "",
        "parentWechat": "",
        "relationship": 1,
        "name": "篮球1",
        "touchTime": "2018-12-27 18:51:11",
        "createdAt": "",
        "updatedAt": ""
    }
}

```


## 2.4 是否是再次购买未结束课程 {#payed-course}
### 请求路径
`GET /api/payed-course`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|String|Y|课程编码|
### 请求示例
无
### 返回参数
无
### 返回示例
```json

```
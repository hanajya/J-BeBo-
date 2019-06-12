# 11.订单管理模块
## 11.1.正式列表 {#order-formal-list}
### 请求路径
`GET /order/formal-list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|status|body|int|N| 订单状态 20待付款 30已付款|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|orderNumber|body|string|Y|订单号|
|createdAt|body|int|Y|下单时间|
|createPersonCode|body|string|Y|下单人|
|orderStatus|body|int|Y|订单状态 20待付款 30已付款 [预约订单]50未开始 60进行中 70已结束|
|amount|body|decimal|Y|订单金额|
|payType|body|decimal|Y|支付方式 10线上 20线下|
|fieldName|body|string|Y|场地名称|
|address|body|string|Y|详细地址|
|userName|body|string|Y|学员名|
|userPhone|body|string|Y|学员手机号|
|courseName|body|string|Y|课程名|
|price|body|string|Y|每期定价|
|levelName|body|string|Y|所选级别|
|stageNum|body|string|Y|所选期数|
|giveNum|body|string|Y|赠送节数|
|courseAmount|body|string|Y|课程总额|
|status|body|int|Y|10可编辑状态 20不可编辑状态|
### 返回示例

```json
{
    "request": "0432a93e-3f52-4bbc-a800-2b6939a2fb5c",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 5,
                "code": "OM000001",
                "merchantCode": "M000002",
                "orderNumber": "15460470049333",
                "type": 10,
                "amount": "100.00",
                "payType": 20,
                "fieldName": "篮球",
                "courseImage": "2.jpg",
                "province": "海南",
                "city": "三亚",
                "district": "南滨",
                "address": "红光山顶",
                "subscribeAt": "",
                "price": "",
                "levelName": "篮球1",
                "stageNum": 1,
                "giveNum": 1,
                "courseAmount": "100.00",
                "userCode": "UM000001",
                "createPersonCode": "AM000002",
                "userName": "篮球1",
                "courseName": "PDS蓝球",
                "stageSection": 8,
                "orderStatus": 30,
                "coachName": "",
                "coachPhone": "",
                "userPhone": "18665736315",
                "fieldCode": "FDM000001",
                "status": "20",
                "createdAt": "2018-12-29 09:30:04",
                "updatedAt": "2018-12-29 09:30:04"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 11.2.体验订单列表 {#order-exprice-list}
### 请求路径
`GET /order/exprice-list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|status|body|int|N| 订单状态 50未开始 60进行中 70已结束|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|orderNumber|body|string|Y|订单号|
|createdAt|body|int|Y|下单时间|
|createPersonCode|body|string|Y|下单人|
|orderStatus|body|int|Y|订单状态 20待付款 30已付款 [预约订单]50未开始 60进行中 70已结束|
|amount|body|decimal|Y|订单金额|
|payType|body|decimal|Y|支付方式 10线上 20线下|
|fieldName|body|string|Y|场地名称|
|address|body|string|Y|详细地址|
|userName|body|string|Y|学员名|
|userPhone|body|string|Y|学员手机号|
|courseName|body|string|Y|课程名|
|price|body|string|Y|每期定价|
|levelName|body|string|Y|所选级别|
|stageNum|body|string|Y|所选期数|
|giveNum|body|string|Y|赠送节数|
|courseAmount|body|string|Y|课程总额|
|status|body|int|Y|10可编辑状态 20不可编辑状态|
### 返回示例

```json
{
    "request": "0c50a0e3-a801-45b5-a7fb-4953ae48dda3",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 6,
                "code": "OM000002",
                "merchantCode": "M000002",
                "orderNumber": "15460478101165",
                "type": 20,
                "amount": "",
                "payType": 20,
                "fieldName": "篮球",
                "courseImage": "2.jpg",
                "province": "海南",
                "city": "三亚",
                "district": "南滨",
                "address": "红光山顶",
                "subscribeAt": "2018-12-29 09:43:30",
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
                "createdAt": "2018-12-29 09:43:30",
                "updatedAt": "2018-12-29 09:43:30"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```



## 11.3.新增订单 {#order-create}
### 请求路径
`POST /order/create`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|type|body|int|Y| 课程类型 10 正式 20 体验|
|fieldCode|body|string|Y| 场地编码|
|courseCode|body|string|Y| 课程编码|
|levelCode|body|string|Y| 级别编码|
|province|body|string|Y| 省|
|city|body|string|Y| 市|
|district|body|string|Y| 区|
|courseCode|body|string|Y| 课程编码|
|phone|body|string|Y| 学员电话|
|price|body|decimal|N| type = 10时必填|
|userCode|body|string|Y| 学员编码|
|section|body|int|N|节数 type = 10时必填|
|stageNum|body|int|N|期数 type = 10时必填|
|giveNum|body|int|N|赠送节数 type = 10时必填|
|name|body|string|N|级别名称 type = 10时必填|

### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "3ac492a6-efec-484d-8370-ddb34971ab20",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 11.4.编辑订单 {#order-modify}
### 请求路径
`POST /order/modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|地址栏携带|
|sign|body|string|N|1表示确认此订单,确认后不可再编辑,0单纯编辑订单|
|type|body|int|Y| 课程类型 10 正式 20 体验|
|fieldCode|body|string|Y| 场地编码|
|courseCode|body|string|Y| 课程编码|
|levelCode|body|string|Y| 级别编码|
|province|body|string|Y| 省|
|city|body|string|Y| 市|
|district|body|string|Y| 区|
|courseCode|body|string|Y| 课程编码|
|phone|body|string|Y| 学员电话|
|price|body|decimal|N| type = 10时必填|
|userCode|body|string|Y| 学员编码|
|section|body|int|N|节数 type = 10时必填|
|stageNum|body|int|N|期数 type = 10时必填|
|giveNum|body|int|N|赠送节数 type = 10时必填|
|name|body|string|N|级别名称 type = 10时必填|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "72203b09-f8a6-4c32-bf0e-1a86c718212f",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 11.5.取消订单 {#order-cancel}
### 请求路径
`POST /order/cancel`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json

```


## 11.6.根据分类查询课程相关数据获取 {#order-course-info}
### 请求路径
`GET /order/course-info`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|int|Y|课程编码 地址栏携带 根据课程code获取该课程的名称、级别与级别，包括提示信息|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|课程code|
|title|body|string|Y|课程名称|
|section|body|int|Y|每期节数|
|levelStage.name|body|string|Y|级别名称|
|levelStage.maxStage|body|int|Y|最大期数 自行循环|
|levelStage.stageNum|body|int|Y|期数|
|levelStage.giveNum|body|int|Y|赠达节数|
### 返回示例

```json
{
    "request": "ed723e8c-ec89-4d9b-9d69-bfaec058e346",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        {
            "title": "PDS蓝球",
            "code": "COR000001",
            "stageCode": "SM000001",
            "section": "8",
            "levelStage": [
                {
                    "code": "LM000002",
                    "name": "篮球",
                    "maxStage": 3,
                    "stageNum": "1",
                    "giveNum": 3
                },
                {
                    "code": "LM000003",
                    "name": "篮球1",
                    "maxStage": 3,
                    "stageNum": "1",
                    "giveNum": 3
                }
            ]
        }
    ]
}
```

## 11.7.新增并确认订单 {#order-create-order-course}
### 请求路径
`POST /order/create-order-course`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|type|body|int|Y| 课程类型 10 正式 20 体验|
|fieldCode|body|string|Y| 场地编码|
|courseCode|body|string|Y| 课程编码|
|levelCode|body|string|Y| 级别编码|
|province|body|string|Y| 省|
|city|body|string|Y| 市|
|district|body|string|Y| 区|
|courseCode|body|string|Y| 课程编码|
|phone|body|string|Y| 学员电话|
|price|body|decimal|N| type = 10时必填|
|userCode|body|string|Y| 学员编码|
|section|body|int|N|节数 type = 10时必填|
|stageNum|body|int|N|期数 type = 10时必填|
|giveNum|body|int|N|赠送节数 type = 10时必填|
|name|body|string|N|级别名称 type = 10时必填|
### 返回示例

```json
{
    "request": "3ac492a6-efec-484d-8370-ddb34971ab20",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 11.8.总平台订单列表 {#order}
### 请求路径
`GET /order`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|merchant_code|body|string|N| 商户code|
### 返回示例

```json
{
    "request": "78fa3761-2a46-4001-945b-beb8f8757519",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
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
                "updatedAt": "2018-12-29 10:45:35"
            },
            {
                "id": 10,
                "code": "OM000002",
                "merchantCode": "M000002",
                "orderNumber": "15462281224888",
                "type": 20,
                "amount": "",
                "payType": 20,
                "fieldName": "篮球",
                "courseImage": "2.jpg",
                "province": "海南",
                "city": "三亚",
                "district": "南滨",
                "address": "红光山顶",
                "subscribeAt": "2018-12-31 11:48:42",
                "price": "",
                "levelName": "",
                "stageNum": "",
                "giveNum": "",
                "courseAmount": "",
                "userCode": "UM000002",
                "createPersonCode": "AM000002",
                "userName": "篮球1",
                "courseName": "PDS蓝球",
                "stageSection": "",
                "orderStatus": 50,
                "coachName": "",
                "coachPhone": "",
                "userPhone": "18665736316",
                "fieldCode": "FDM000001",
                "status": "20",
                "createdAt": "2018-12-31 11:48:42",
                "updatedAt": "2018-12-31 11:48:42"
            }
        ],
        "currentPage": 1,
        "total": 2,
        "perPage": "10",
        "lastPage": 1
    }
}
```

## 11.9.查询学员信息 {#getuserinfo}
### 请求路径
`GET /order/getuserinfo`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|phone|body|string|Y| 用户手机号|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "3ac492a6-efec-484d-8370-ddb34971ab20",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```

## 11.10.分类下的场地 {#categoryfield}
### 请求路径
`GET /order/categoryfield`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|categoryCode|body|string|Y| 分类编码|
### 请求示例
无
### 返回参数
无
### 返回示例

```json

```
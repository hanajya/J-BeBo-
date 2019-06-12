# 8.课程管理-课程列表模块
## 8.1.正式/体验课程列表 {#course-list}
### 请求路径
`GET /course/list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|category_code|body|int|N|分类筛选|
|type|body|int|Y|10 正式 20 体验|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|title|body|string|Y|课程名称|
|category_code|body|int|Y|分类id|
|category_name|body|string|Y|分类名称|
|price|body|decimal|Y|每期定价|
|content|body|string|Y|内容|
|level_group|body|array|Y|级别|
|stage_code|body|array|Y|期数编号|
|status|body|int|Y|状态 10启用 20未启用|
|createdAt|body|string|Y|创建时间|
### 返回示例

```json
{
    "request": "8a8a070e-9e6f-4f57-b6b6-8b72c6b7b491",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 4,
                "code": "COR000001",
                "merchantCode": "M000002",
                "title": "PDS蓝球",
                "content": "xxx",
                "price": "",
                "image": "2.jpg",
                "categoryCode": "CTM000001",
                "discount": "",
                "stageCode": "SM000001",
                "label": [
                    "龙大人",
                    "lsls"
                ],
                "status": 10,
                "type": 20,
                "createdAt": "2018-12-27 15:48:07",
                "updatedAt": "2018-12-27 15:48:07"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 8.3.新增课程 {#course-create}
### 请求路径
`POST /course/create`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|title|body|int|Y|课程名称|
|price|body|decimal|N|每期定价 type = 10，必填|
|content|body|int|Y|内容|
|level|body|int|N|级别 多个 type = 10，必填|
|stage|body|int|N|级别下的最大节数显示 type = 10，必填|
|type|body|int|Y|类型 10正式 20体验|
|image|body|string|Y|图片|
|categoryCode|body|string|Y|分类编码|
|discount|body|string|N|优惠|
|stageCode|body|string|Y|期数编码 单选|
|levelCode|body|array|Y|级别编码 多选|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "62557c2b-e51e-4b25-a519-b4f8d53e41e0",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 8.4.编辑课程 {#course-modify}
### 请求路径
`POST /course/modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|int|Y|课程编码 地址栏携带|
|title|body|int|N|课程名称|
|price|body|decimal|N|每期定价 type = 10，必填|
|content|body|int|N|内容|
|level|body|int|N|级别 多个 type = 10，必填|
|stage|body|int|N|级别下的最大节数显示 type = 10，必填|
|type|body|int|Y|类型 10正式 20体验|
|image|body|string|N|图片|
|categoryCode|body|string|N|分类编码|
|discount|body|string|N|优惠|
|stageCode|body|string|N|期数编码 单选|
|levelCode|body|array|N|级别编码 多选|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "c053e859-512b-465c-9f00-c75e589526c0",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```



## 8.5.删除课程 {#course-delete}
### 请求路径
`POST /course/delete`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|int|Y|课程编码 地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "845293e8-bb7b-472f-bd16-687d8a50aa75",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```

## 8.6.课程详情 {#course-detail}
### 请求路径
`GET /course/detail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|int|Y|课程编码 地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "dbcec55f-4484-4f4b-b9fa-22d3ea7480d8",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 5,
        "code": "COR000001",
        "merchantCode": "M000002",
        "title": "PDS蓝球",
        "content": "xxx",
        "price": "",
        "image": "2.jpg",
        "categoryCode": "CTM000001",
        "discount": "",
        "stageCode": "SM000001",
        "label": "[\"\\u9f99\\u5927\\u4eba\",\"lsls\"]",
        "status": 10,
        "type": 20,
        "createdAt": "2018-12-27 16:32:48",
        "updatedAt": "2018-12-27 16:32:48"
    }
}
```

## 8.7.总平台课程列表 {#course}
### 请求路径
`GET /course`
### 请求参数
无
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "8a8a070e-9e6f-4f57-b6b6-8b72c6b7b491",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 4,
                "code": "COR000001",
                "merchantCode": "M000002",
                "title": "PDS蓝球",
                "content": "xxx",
                "price": "",
                "image": "2.jpg",
                "categoryCode": "CTM000001",
                "discount": "",
                "stageCode": "SM000001",
                "label": [
                    "龙大人",
                    "lsls"
                ],
                "status": 10,
                "type": 20,
                "createdAt": "2018-12-27 15:48:07",
                "updatedAt": "2018-12-27 15:48:07"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```
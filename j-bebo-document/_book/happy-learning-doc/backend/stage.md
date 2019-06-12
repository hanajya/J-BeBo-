# 10.课程管理-期数模块
## 10.1.级别列表 {#stage-list}
### 请求路径
`GET /stage/list`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|code|body|string|Y|期数编码|
|section|body|int|Y|每期节数|
|createdAt|body|int|Y|创建时间|
### 返回示例

```json
{
    "request": "a0264c1b-1de0-4c50-a428-afbaef7862f8",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 1,
                "code": "SM000001",
                "merchantCode": "M000002",
                "section": 8,
                "createdAt": "2018-12-27 09:50:43",
                "updatedAt": "2018-12-27 09:50:43"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 10.2.新增期数{#stage-create}
### 请求路径
`POST /stage/create`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|section|body|int|Y|每期节数|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "a90c7c40-07fc-4a76-b176-da8e3e898673",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 10.3.编辑期数 {#stage-modify}
### 请求路径
`POST /stage/modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|section|body|int|N|每期节数|
|code|body|string|Y|期数编码 地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "6426515a-a376-4f70-958b-41ee551ec0f0",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 10.4.删除期数 {#stage-delete}
### 请求路径
`POST /stage-delete`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|期数编码 地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "99462338-cc25-4f3a-8a90-c1a3a373e136",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 10.5.期数详情 {#stage-detail}
### 请求路径
`GET /stage/detail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|期数编码 地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "a5d4bc0d-8173-4c5d-9efc-f717921ddb0c",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 1,
        "code": "SM000001",
        "merchantCode": "M000002",
        "section": 8,
        "createdAt": "2018-12-27 09:50:43",
        "updatedAt": "2018-12-27 09:50:43"
    }
}
```

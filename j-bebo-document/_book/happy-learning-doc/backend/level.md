# 9.课程管理-级别模块
## [9.1.级别列表](backend/level.md#level-list)
### 请求路径
`GET /level/list`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|name|body|string|Y|级别名称|
|risk|body|int|Y|风险提示|
|condition|body|string|Y|赠送规则 多少期|
|value|body|string|Y|赠送规则 赠送多少节|
|maxStage|body|decimal|Y|最大期数|
|status|body|int|Y|状态 10启用 20未启用|
|createdAt|body|int|Y|创建时间|
### 返回示例

```json

```


## 9.2.新增级别 {#level-create}
### 请求路径
`POST /level/create`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|name|body|string|Y|级别名称|
|risk|body|string|N|风险提示|
|condition|body|string|Y|赠送规则 多少期|
|value|body|string|Y|赠送规则 赠送多少节|
|max_stage|body|int|Y|最大期数|
|price|body|decimal|Y|价格|
|order|body|int|Y|排序|
|status|body|int|Y|状态 10启用 20未启用 必选其一|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "76e0e2c6-42a2-46ee-b88b-ecd53edeb053",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 9.3.编辑级别 {#level-modify}
### 请求路径
`POST /level/modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|级别编码 地址栏携带|
|name|body|string|N|级别名称|
|risk|body|string|N|风险提示|
|condition|body|string|Y|赠送规则 多少期|
|value|body|string|Y|赠送规则 赠送多少节|
|max_stage|body|int|N|最大期数|
|price|body|decimal|Y|价格|
|order|body|int|N|排序|
|status|body|int|Y|状态 10启用 20未启用 必选其一|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "8ff638ce-8e59-421c-bbef-e92318a688a7",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 9.4.删除级别 {#level-delete}
### 请求路径
`POST /level/delete`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|级别编码 地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "59cbf3a6-e490-4f19-9b3e-f267656ba9ee",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 9.5.级别详情 {#level-detail}
### 请求路径
`GET /level/detail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|级别编码 地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "2e5cf5ca-3d90-41fb-b746-a23896b03d7e",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 6,
        "code": "LM000002",
        "merchantCode": "M000002",
        "name": "篮球",
        "risk": "",
        "order": 2,
        "maxStage": 3,
        "status": 10,
        "createdAt": "2018-12-27 13:42:18",
        "updatedAt": "2018-12-27 13:42:18"
    }
}
```
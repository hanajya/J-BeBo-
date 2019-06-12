# 7.课程分类管理模块
## 7.1.商户分类列表 {#category-list}
### 请求路径
`GET /category/list`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|name|body|string|Y|分类名称|
|status|body|int|Y|状态 10启用 20未启用|
|createdAt|body|int|Y|创建时间|
### 返回示例

```json
{
    "request": "76420b9b-808b-42af-9605-f292e8e0e12e",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 1,
                "code": "CTM000001",
                "merchantCode": "M000002",
                "name": "篮球",
                "order": 1,
                "status": "10",
                "createdAt": "2018-12-25 16:38:44",
                "updatedAt": "2018-12-25 16:38:44"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```



## 7.2.商户新增分类 {#category-create}
### 请求路径
`POST /category/create`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|name|body|string|Y|分类名|
|status|body|int|Y|状态 10启用 20未启用|
|order|body|int|Y|排序|
### 请求示例
无
### 返回参数

```json
{
    "request": "02efe80b-f32c-465c-8db0-4bb02a9b6f99",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        true
    ]
}
```



## 7.3.商户编辑分类 {#category-modify}
### 请求路径
`POST /category/modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|name|body|string|N|分类名|
|status|body|int|N|状态 10启用 20未启用|
|order|body|int|Y|排序|
### 请求示例
无
### 返回参数

```json
{
    "request": "6c39741c-b168-4494-ae17-8c412488bf8c",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        true
    ]
}
```



## 7.4.商户删除分类 {#category-delete}
### 请求路径
`POST /category/delete`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|N|分类编码 地址栏携带|
### 请求示例
无
### 返回参数

```json
{
    "request": "f44ebe51-6ba6-4016-a2c1-93b56ab1d6f7",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        1
    ]
}
```


## 7.5.商户分类详情 {#category-detail}
### 请求路径
`GET /category/detail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|N|分类编码 地址栏携带|
### 请求示例
无
### 返回参数

```json
{
    "request": "f5cc591f-e961-4d5b-aebc-f0005734dd11",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 1,
        "code": "CTM000001",
        "merchantCode": "M000002",
        "name": "篮球",
        "order": 1,
        "status": "10",
        "createdAt": "2018-12-25 16:38:44",
        "updatedAt": "2018-12-25 16:38:44"
    }
}
```


## 7.6.总平台分类列表 {#category}
### 请求路径
`GET /category`
### 请求参数
无
### 请求示例
无
### 返回参数

```json
{
    "request": "76420b9b-808b-42af-9605-f292e8e0e12e",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 1,
                "code": "CTM000001",
                "merchantCode": "M000002",
                "name": "篮球",
                "order": 1,
                "status": "10",
                "createdAt": "2018-12-25 16:38:44",
                "updatedAt": "2018-12-25 16:38:44"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```
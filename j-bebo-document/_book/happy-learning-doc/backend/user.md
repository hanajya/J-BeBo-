# 6.用户模块
## 6.1.登陆 {#admin-login}
### 请求路径
`POST /admin/login`	总后台
`POST /admin/merchant-login`	商户后台
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|username|body|string|Y|用户名|
|password|body|string|Y|密码|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "efd8e536-53bc-4cf3-b7ba-e412dd47e5b0",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "accessToken": "wwNCMELwyGvp7oIEGqsHVqW4IYChUaoBQeI9atTw"
    }
}
```

## 6.2.总平台用户修改 {#admin-modify}
### 请求路径
`POST /admin/modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|编码 地址栏上携带|
|username|body|string|N|用户名|
|password|body|string|N|密码|
|name|body|string|N|姓名|
|phone|body|string|N|手机号|
|type|body|int|Y|类型 10 总后台超级管理员 20总后台管理员 必选其一|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "f9f1a1f1-9012-413c-9cf9-2b7a891ae47a",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        true
    ]
}
```

## 6.3.总平台用户列表 {#admin-list}
### 请求路径
`GET /admin/list`
### 请求参数
无
### 请求参数
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|id|
|code|body|string|Y|编码|
|username|body|string|Y|用户名|
|password|body|string|Y|密码|
|name|body|string|Y|姓名|
|phone|body|string|Y|手机号|
|createdAt|body|int|Y|创建时间|
### 返回示例

```json
{
    "request": "edc6234e-8c1e-433e-bdc1-9ab3de8eff65",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 1,
                "code": "AM000001",
                "username": "admin",
                "password": "admin",
                "name": "superman1",
                "phone": "18665736315",
                "type": "30",
                "merchantCode": "",
                "createdAt": "2018-12-24 14:30:55",
                "updatedAt": "2018-12-24 16:03:47"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```

## 6.4.总平台用户添加 {#admin-create}
### 请求路径
`POST /admin/create`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|username|body|string|Y|用户名|
|password|body|string|Y|密码|
|name|body|string|Y|姓名|
|phone|body|string|Y|手机号|
|type|body|int|Y|类型 10 总后台超级管理员 20总后台管理员 |
### 返回参数
无
### 返回示例

```json
{
    "request": "491aa31d-e744-43f7-b5c8-b94c59b92d02",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        true
    ]
}
```

## 6.5.总平台用户删除 {#admin-delete}
### 请求路径
`POST /admin/delete`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|编码 地址栏上携带|
### 返回参数
无
### 返回示例

```json
{
    "request": "b6dd2975-f66e-4a3f-9bc1-cb3b2a249da2",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        1
    ]
}
```


## 6.6.总平台用户详情 {#admin-detail}
### 请求路径
`GET /admin/detail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|编码 地址栏上携带|
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|id|
|code|body|string|Y|编码|
|username|body|string|Y|用户名|
|password|body|string|Y|密码|
|name|body|string|Y|姓名|
|phone|body|string|Y|手机号|
|createdAt|body|int|Y|创建时间|
|updatedAt|body|int|Y|更新时间|
### 返回示例

```json
{
    "request": "31918bcc-ed5e-41b9-b93f-4f574cf86012",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 1,
        "code": "AM000001",
        "username": "admin",
        "password": "admin",
        "name": "superman1",
        "phone": "18665736315",
        "type": "30",
        "merchantCode": "",
        "createdAt": "2018-12-24 14:30:55",
        "updatedAt": "2018-12-24 16:03:47"
    }
}
```
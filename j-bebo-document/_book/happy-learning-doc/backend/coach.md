# 14.教练管理模块
## 14.1.教练列表 {#coach-list}
### 请求路径
`GET /coach/list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|category_code|body|int|N|分类id|
|name|body|int|N|教练姓名|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|categoryCode|body|int|Y|分类id|
|categoryName|body|int|Y|分类name|
|name|body|string|Y|名称|
|avatar|body|string|Y|头像|
|sex|body|string|Y|性别|
|age|body|int|Y|年龄|
|phone|body|string|Y|手机号|
|expertise|body|array|Y|专长|
|username|body|array|Y|登陆帐号|
|password|body|array|Y|密码|
|createdAt|body|int|Y|创建时间|
|categoryName|body|string|Y|分类名称|
### 返回示例

```json
{
    "request": "5961263b-83ec-4fdd-818b-eacc489b12c5",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 3,
                "code": "CO000001",
                "merchantCode": "M000002",
                "username": "龙大人",
                "password": "$2y$10$QAOU4D9l5JIW2/QMJuyKJOCedH11Uk.rIPCAG/tgaD0F9xP9iM0YG",
                "avatar": "",
                "name": "篮球",
                "sex": "",
                "age": 16,
                "phone": "18665736315",
                "expertise": [
                    "music",
                    "movie",
                    "idol"
                ],
                "status": 20,
                "createdAt": "2018-12-26 16:04:46",
                "updatedAt": "2018-12-26 16:04:46",
                "coachCode": "CO000001",
                "categoryCode": "CTM000001",
                "categoryName": "篮球"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 14.2.新增教练 {#coach-create}
### 请求路径
`POST /coach/create`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|categories|body|object|N|分类编码|
|name|body|string|N|姓名|
|sex|body|int|N|性别 10 未知 20 男 30 女|
|age|body|int|N|年龄|
|avatar|body|string|N|头像地址|
|phone|body|int|Y|手机号|
|expertise|body|array|Y|专长|
|username|body|string|Y|登陆帐号|
|password|body|string|Y|密码|
|status|body|string|Y|10启用 20 停用 默认启用|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "3c432b78-c647-4178-86ff-8733e9a67ad4",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 14.3.编辑教练 {#coach-modify}
### 请求路径
`POST /coach/modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|categories|body|object|N|分类编码|
|name|body|string|N|姓名|
|sex|body|int|N|性别 10 未知 20 男 30 女|
|age|body|int|N|年龄|
|avatar|body|string|N|头像地址|
|phone|body|int|N|手机号|
|expertise|body|array|N|专长|
|username|body|string|N|登陆帐号|
|password|body|string|N|密码|
|status|body|string|Y|10启用 20 停用 默认启用 必有其一|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "64f405d7-568c-4d10-a22d-42fb17523405",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 14.4.删除教练 {#coach-delete}
### 请求路径
`POST /coach/delete`
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
{
    "request": "bc25c1c6-3d37-4a34-9867-fed049891311",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```
## 14.5.教练详情 {#coach-detail}
### 请求路径
`GET /coach/detail`
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
{
    "request": "8e829371-9bf6-42fc-bd35-51d21f9115e5",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 9,
        "code": "CO000001",
        "merchantCode": "M000002",
        "username": "龙大人",
        "password": "$2y$10$QAOU4D9l5JIW2/QMJuyKJOCedH11Uk.rIPCAG/tgaD0F9xP9iM0YG",
        "avatar": "",
        "name": "篮球",
        "sex": "",
        "age": 16,
        "phone": "18665736315",
        "expertise": [
            "music",
            "movie",
            "idol"
        ],
        "status": 20,
        "createdAt": "2018-12-26 16:04:46",
        "updatedAt": "2018-12-26 16:04:46"
    }
}
```


## 14.6.总平台教练列表 {#coach}
### 请求路径
`GET /coach`
### 请求参数
无
### 请求示例
无
### 返回参数
无
### 返回示例

```json

```


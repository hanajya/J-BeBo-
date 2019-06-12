# 13.场地管理模块
## 13.1.场地列表 {#field-list}
### 请求路径
`GET /field/list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|category_code|body|int|N|分类id|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|categoryCode|body|int|Y|分类id|
|categoryName|body|int|Y|分类name|
|name|body|string|Y|场地名|
|address|body|string|Y|地点|
|image|body|string|Y|场地图|
|createdAt|body|int|Y|创建时间|
### 返回示例

```json
{
    "request": "2f9d0ba5-9fe6-4bb5-9474-953d2e6e4e3a",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 1,
                "code": "FDM000001",
                "merchantCode": "M000002",
                "name": "篮球",
                "image": "https://www.baidu.com",
                "phone": "18665736315",
                "categoryCode": "CTM000001",
                "province": "海南",
                "city": "三亚",
                "district": "南滨",
                "address": "红光山顶",
                "createdAt": "2018-12-26 17:08:52",
                "updatedAt": "2018-12-26 17:08:52"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```



## 13.2.新增场地 {#field-create}
### 请求路径
`POST /field/create`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|category_code|body|int|Y|分类编码|
|name|body|string|Y|场地名|
|address|body|string|N|详细地址|
|province|body|string|Y|省|
|city|body|string|Y|市|
|district|body|string|Y|区|
|image|body|string|Y|场地图|
|phone|body|string|N|电话|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "aa05d260-909c-4667-a97a-e7d385f480ed",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 13.3.编辑场地 {#field-modify}
### 请求路径
`POST /field/modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|category_code|body|int|N|分类编码|
|name|body|string|N|场地名|
|address|body|string|N|详细地址|
|province|body|string|N|省|
|city|body|string|N|市|
|district|body|string|N|区|
|image|body|string|N|场地图|
|phone|body|string|N|电话|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "08926f55-8c85-432d-bb74-b9eb3c91e09c",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 13.4.删除场地 {#field-delete}
### 请求路径
`POST /field/delete`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|int|Y|地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "71efb9d0-919e-4975-90d4-115de07a0311",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 13.5.场地详情 {#field-detail}
### 请求路径
`GET /field/detail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|int|Y|地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "191d56d8-accb-42b5-8767-0c70708f4012",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 1,
        "code": "FDM000001",
        "merchantCode": "M000002",
        "name": "篮球",
        "image": "https://www.baidu.com",
        "phone": "18665736315",
        "categoryCode": "CTM000001",
        "province": "海南",
        "city": "三亚",
        "district": "南滨",
        "address": "红光山顶",
        "createdAt": "2018-12-26 17:08:52",
        "updatedAt": "2018-12-26 17:08:52"
    }
}
```


## 13.6.总平台场地列表 {#field}
### 请求路径
`GET /field`
### 请求参数
无
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "542e052e-6471-4b43-bbcc-2108de8d7f73",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 1,
                "code": "FDM000001",
                "merchantCode": "M000002",
                "name": "篮球",
                "image": "https://www.baidu.com",
                "phone": "18665736315",
                "categoryCode": "CTM000001",
                "province": "海南",
                "city": "三亚",
                "district": "南滨",
                "address": "红光山顶",
                "createdAt": "2018-12-26 17:08:52",
                "updatedAt": "2018-12-26 17:08:52"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 13.7.省 {#province}
### 请求路径
`GET /field/province`
### 请求参数
无
### 请求示例
无
### 返回参数
无
### 返回示例

```json

```

## 13.8.市 {#city}
### 请求路径
`GET /field/city`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|provinceId|body|int|Y|省id|
### 请求示例
无
### 返回参数
无
### 返回示例

```json

```


## 13.9.区 {#district}
### 请求路径
`GET /field/district`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|cityId|body|int|Y|市id|
### 请求示例
无
### 返回参数
无
### 返回示例

```json

```
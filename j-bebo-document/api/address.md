#5.收货地址模块
### 5.1.收货地址列表 {#address-list}
### 请求路径
`GET /api/address-list`
### 请求参数
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|consignee_name|body|string|Y|收货人姓名|
|consignee_mobile|body|string|Y|收货人地址|
|province|body|string|Y|省|
|city|body|string|Y|市|
|district|body|string|Y|区|
|address|body|string|Y|详细地址|
|code|body|string|Y|邮编|
|is_default|body|string|Y|是否是默认地址 1是默认地址|
###返回示例
```json
{
    "status": 200,
    "message": "",
    "data": [
        {
            "id": 6,
            "user_id": 10,
            "consignee_name": "syuka",
            "consignee_mobile": "18665736315",
            "province": "广东省",
            "city": "深圳市",
            "district": "南山区",
            "address": "深圳湾B栋10楼",
            "code": "500000",
            "is_default": 0,
            "create_time": "2019-06-11 09:50:13",
            "update_time": "2019-06-11 09:55:43"
        }
    ]
}
```

### 5.2.添加或编辑收货地址 {#set-address}
### 请求路径
`POST /api/set-address`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|consignee_name|body|string|Y|收货人姓名|
|consignee_mobile|body|string|Y|收货人地址|
|province|body|string|Y|省 如广东省|
|city|body|string|Y|市 如深圳市|
|district|body|string|Y|区 如南山区|
|address|body|string|Y|详细地址|
|code|body|string|N|邮编|
|address_id|body|string|N|编辑时使用|
### 返回参数
无
###返回示例
```json
{
    "status": 200,
    "message": "处理成功"
}
```

### 5.3.设置默认收货地址 {#set-default}
### 请求路径
`POST /api/set-default`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|header|int|Y|地址id|
### 返回参数
无
### 返回示例
```json
{
    "status": 200,
    "message": "设置成功"
}
```

### 5.4.删除收货地址 {#del-address}
### 请求路径
`POST /api/del-address`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|header|int|Y|地址id|
### 返回参数
无
### 返回示例
```json
{
    "status": 200,
    "message": "删除成功"
}
```




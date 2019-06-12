#5.订单模块
## 5.1.订单详情-创建订单 {#order-createOrder}
### 请求路径
`POST /order/createorder`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|type|body|int|Y|订单类型|
|fieldCode|body|string|Y|场地编码|
|courseCode|body|string|Y|课程编码|
|levelCode|body|string|Y|级别编码|
|stageNum|body|int|Y|期数|
|giveNum|body|int|Y|赠送节数|
|stageSection|body|int|Y|每期节数|
### 请求示例
无
### 返回参数
无
返回示例 正式课程订单返回
```json
{
    "request": "506c8456-18b9-428e-84e9-706bf660f7f8",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "appId": "wx3c53cddd8bdb6d97",
        "nonceStr": "5c3c236ee1ea5",
        "package": "prepay_id=wx14135141786062177d5eaf4d2870974825",
        "signType": "MD5",
        "paySign": "EC6E324292055980668F5C0F581E2F5E",
        "timestamp": "1547445102"
    }
}
```

###  返回示例 体验课程返回
```json 
{
	
    "request": "3421cf0d-a1a5-4376-87ad-a0a866346f7d",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        true
    ]
	
}
```




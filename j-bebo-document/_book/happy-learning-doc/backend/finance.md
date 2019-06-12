# 17.财务管理模块
## 17.1.财务列表 {#finance-list}
### 请求路径
`GET /finance/list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|user_name|body|string|N|学员姓名|
|order_number|body|string|N|订单号|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|userName|body|string|Y|学员姓名|
|orderNumber|body|string|Y|订单号|
|amount|body|decimal|Y|消费金额|
|createdAt|body|int|Y|消费时间|
### 返回示例

```json
{
    "request": "da41f64a-1a2c-4b6b-824f-3b0b354db911",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [],
        "currentPage": 1,
        "total": 0,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 17.2.总金额 {#finance-total}
### 请求路径
`GET /finance/total`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|totalMoney|body|int|Y|学员总金额|
### 返回示例

```json
{
    "request": "1ffa6dd0-a117-4947-a8b6-5fb60cb1a7c4",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "totalMoney": 0
    }
}
```

## 17.3.总平台账务列表 {#finance}
### 请求路径
`GET /finance`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|merchant_code|body|string|N|商户编码|
### 返回示例

```json
{
    "request": "06abddce-03b3-4384-b52b-df65b3ad6cbf",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [],
        "currentPage": 1,
        "total": 0,
        "perPage": "10",
        "lastPage": 1
    }
}
```
# 19.客户后台帐号及小程序资料
## 19.1.新增资料 {#merchant}
### 请求路径
`POST /merchant`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|name|body|string|Y|商户名|
|phone|body|string|Y|商户电话|
|username|body|string|Y|登陆帐号|
|password|body|string|Y|登陆密码|
|content|body|string|N|简介|
|identity_card_front|body|string|N|身份证正面|
|identity_card_obverse|body|string|N|身份证反面|
|business_license|body|string|N|营业执照|
|amount|body|string|N|金额|
|key|body|string|Y|小程序key|
|secret|body|string|Y|小程序密钥|
|mch_key|body|string|Y|商户账号|
|mch_secret|body|string|Y|商户密钥|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "9fbbe91b-280a-461f-a20a-7464b4f4362d",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 19.2.编辑资料 {#merchant}
### 请求路径
`PUT /merchant`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|商户code 地址栏携带|
|name|body|string|Y|商户名|
|phone|body|string|Y|商户电话|
|username|body|string|Y|登陆帐号|
|password|body|string|Y|登陆密码|
|content|body|string|N|简介|
|identity_card_front|body|string|N|身份证正面|
|identity_card_obverse|body|string|N|身份证反面|
|business_license|body|string|N|营业执照|
|amount|body|string|N|金额|
|key|body|string|Y|小程序key|
|secret|body|string|Y|小程序密钥|
|mch_key|body|string|Y|商户账号|
|mch_secret|body|string|Y|商户密钥|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "9fbbe91b-280a-461f-a20a-7464b4f4362d",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```

## 19.3.资料详情 {#merchant}
### 请求路径
`GET /merchant`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|商户code 地址栏携带|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|name|body|string|Y|商户名|
|phone|body|string|Y|商户电话|
|username|body|string|Y|登陆帐号|
|password|body|string|Y|登陆密码|
|merchantInfo.content|body|string|N|简介|
|identity_card_front|body|string|N|身份证正面|
|identity_card_obverse|body|string|N|身份证反面|
|business_license|body|string|N|营业执照|
|amount|body|string|N|金额|
|merchantInfo.key|body|string|Y|小程序key|
|merchantInfo.secret|body|string|Y|小程序密钥|
|merchantInfo.mch_key|body|string|Y|商户账号|
|merchantInfo.mch_secret|body|string|Y|商户密钥|
### 返回示例

```json
{
    "request": "d2941ac8-461d-444c-8765-991407ee429e",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 8,
        "code": "M000009",
        "name": "篮球1",
        "phone": "18665736316",
        "identityCardFront": "",
        "identityCardObverse": "",
        "businessLicense": "",
        "amount": "",
        "createdAt": "2019-01-02 11:42:26",
        "updatedAt": "2019-01-02 11:42:26",
        "username": "admin",
        "identityCardFrontUrl": "",
        "identityCardObverseUrl": "",
        "businessLicenseUrl": "",
        "merchantInfo": {
            "id": 1,
            "merchantCode": "M000009",
            "type": 0,
            "key": "wx3c53cddd8bdb6d97",
            "secret": "ac6a73d4bd35f6926c0aeb4904978bba",
            "mchKey": "1502083051",
            "mchSecret": "89caf128b2634bfd4a5a3yy53afe6qyd",
            "content": "x66xx",
            "createdAt": "2019-01-02 11:42:26",
            "updatedAt": "2019-01-02 11:42:26"
        }
    }
}
```


### 19.4.资料列表 {#merchant}
### 请求路径
`GET /merchant`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|name|body|string|Y|商户名|
|phone|body|string|Y|商户电话|
|username|body|string|Y|登陆帐号|
|password|body|string|Y|登陆密码|
|merchantInfo.content|body|string|N|简介|
|identity_card_front|body|string|N|身份证正面|
|identity_card_obverse|body|string|N|身份证反面|
|business_license|body|string|N|营业执照|
|amount|body|string|N|金额|
|merchantInfo.key|body|string|Y|小程序key|
|merchantInfo.secret|body|string|Y|小程序密钥|
|merchantInfo.mch_key|body|string|Y|商户账号|
|merchantInfo.mch_secret|body|string|Y|商户密钥|
### 返回示例

```json
{
    "request": "c653e128-33a8-4a1b-b084-49eac64632b8",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 8,
                "code": "M000009",
                "name": "篮球1",
                "phone": "18665736316",
                "identityCardFront": "",
                "identityCardObverse": "",
                "businessLicense": "",
                "amount": "",
                "createdAt": "2019-01-02 11:42:26",
                "updatedAt": "2019-01-02 11:42:26",
                "merchantInfo": {
                    "id": 1,
                    "merchantCode": "M000009",
                    "type": 0,
                    "key": "wx3c53cddd8bdb6d97",
                    "secret": "ac6a73d4bd35f6926c0aeb4904978bba",
                    "mchKey": "1502083051",
                    "mchSecret": "89caf128b2634bfd4a5a3yy53afe6qyd",
                    "content": "x66xx",
                    "createdAt": "2019-01-02 11:42:26",
                    "updatedAt": "2019-01-02 11:42:26"
                }
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 19.5.删除资料 {#merchant}
### 请求路径
`Delete /merchant`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|商户code 地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json

```
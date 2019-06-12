# 18.关于我们模块
## 18.1.关于我们 {#aboutus-list}
### 请求路径
`GET /aboutus/list`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|companyLogo|body|string|Y|logo|
|companyName|body|string|Y|公司名称|
|desc|body|string|Y|简介|
|customServiceMobile|body|string|Y|客服电话|
### 返回示例

```json
{
    "request": "9a05132f-0ad0-4a24-a8dd-4ae6c32abadf",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 1,
        "merchantCode": "M00000B",
        "companyLogo": "www.hdl",
        "companyName": "龙歌歌",
        "desc": "漫山遍野",
        "customServiceMobile": "18665736315",
        "createdAt": "2019-01-06 14:26:31",
        "updatedAt": "2019-01-06 14:26:31"
    }
}
```


## 18.2.新增或更新我们 {#aboutus-create-modify}
### 请求路径
`POST /aboutus/create-modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|company_logo|body|string|Y|logo|
|company_name|body|string|Y|公司名称|
|desc|body|string|Y|简介|
|custom_service_mobile|body|string|Y|客服电话|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "da3dbdb0-3e69-490c-b075-73fb7da2533d",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```

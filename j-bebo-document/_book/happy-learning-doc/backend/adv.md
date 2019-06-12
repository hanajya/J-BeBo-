# 12.banner管理模块
## 12.1.商户广告列表 {#adv-list}
### 请求路径
`GET /adv/list`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|id|body|int|Y|序号|
|code|body|string|Y|编号|
|content|body|string|Y|图片|
|connect|body|string|Y|跳转连接|
|status|body|int|Y|状态 10待用 20启用 30停用|
|createdAt|body|int|Y|创建时间|
### 返回示例

```json
{
    "request": "13693ae2-7ba2-4502-86b2-21e70590aa34",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 2,
                "code": "AD000001",
                "merchantCode": "M000002",
                "position": 10,
                "title": "",
                "content": "https://www.baidu.com",
                "extend": "",
                "order": 1,
                "startAt": "",
                "endAt": "",
                "connect": "https://www.baidu.com",
                "status": 10,
                "createdAt": "2018-12-26 11:52:14",
                "updatedAt": "2018-12-26 11:52:14"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 12.2.商户新增广告 {#adv-create}
### 请求路径
`POST /adv/create`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|content|body|string|Y|图片|
|connect|body|string|Y|输入链接页面地址|
|status|body|string|Y|默认为10待用 ，20启用 30 停用|
|order|body|int|Y|排序|

### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "444d0bfb-4b8d-4e72-9ad5-3b0ab8bef040",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```



## 12.3.商户编辑广告{#adv-modify}
### 请求路径
`POST /adv/modify`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|编码 地址栏携带|
|content|body|string|N|图片|
|connect|body|string|N|输入链接页面地址|
|status|body|string|N|默认为10待用 ，20启用 30 停用|
|order|body|int|Y|排序|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "0a3ae155-9e2d-4595-bfa4-8a68961927fe",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```



## 12.4.商户删除广告 {#adv-delete}
### 请求路径
`POST /adv/delete`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|编码 地址栏携带|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "c9283eea-7f1d-44f1-a176-11d59db4d8fe",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```



## 12.5.商户启用/停用 {#adv-modify-status}
### 请求路径
`POST /adv/modify-status`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|编码 地址栏携带|
|status|body|int|Y|操作状态  10待启用 20启用 30停用|
### 请求示例
无
### 返回参数
无
### 返回示例

```json
{
    "request": "45663a91-cf98-4942-98bd-3bc916935ad8",
    "code": 0,
    "message": "request_handle_successful",
    "data": []
}
```


## 12.6.商户广告详情 {#adv-detail}
### 请求路径
`GET /adv/detail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|地址栏携带|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|地址栏携带|
|content|body|string|Y|内容|
|connect|body|string|Y|跳转链接|
|status|body|string|Y|状态 10待启用 20启用 30停用|
|createdAt|body|string|Y|创建时间|
### 返回示例

```json
{
    "request": "2de718c0-6f23-4c1c-b2a3-c3964d6ec8bf",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "id": 2,
        "code": "AD000001",
        "merchantCode": "M000002",
        "position": 10,
        "title": "",
        "content": "https://www.baidu.com",
        "extend": "",
        "order": 1,
        "startAt": "",
        "endAt": "",
        "connect": "https://www.baidu.com",
        "status": 10,
        "createdAt": "2018-12-26 11:52:14",
        "updatedAt": "2018-12-26 12:25:05"
    }
}
```



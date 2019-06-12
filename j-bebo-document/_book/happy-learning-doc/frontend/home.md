#1.首页模块
## 1.1.首页banner图 {#banner}
### 请求路径
`GET /api/banner`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|title|body|string|N|banner图标题|
|content|body|string|Y|图片链接|
|connect|body|string|Y|跳转链接|
### 返回示例
```json
{
    "request": "5ee22c3f-fe4e-4681-9e7d-26c8dd7dcb39",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        {
            "title": "",
            "content": "https://www.baidu.com",
            "connect": "https://www.baidu.com"
        }
    ]
}
```


## 1.2.课程分类 {#category}
### 请求路径
`GET /api/category`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|课程分类code|
|name|body|string|Y|课程分类名|
### 返回示例
```json
{
    "request": "14660937-e331-4470-bce2-32725f05a96c",
    "code": 0,
    "message": "request_handle_successful",
    "data": [
        {
            "id": 1,
            "code": "CTM000001",
            "merchantCode": "M000009",
            "name": "篮球",
            "order": 1,
            "status": "10",
            "createdAt": "2018-12-25 16:38:44",
            "updatedAt": "2018-12-25 16:38:44"
        }
    ]
}
```


## 1.3.课程报名 {#enrollment}
### 请求路径
`GET /api/enrollment`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|课程分类code 地址栏携带|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|课程code|
|title|body|string|Y|课程标题|
|price|body|decimal|Y|每期定价|
|image|body|string|Y|图片链接|
### 返回示例
```json
{
    "request": "0d8cd2f1-9af6-45fe-97f3-ee32fee50ec8",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 5,
                "code": "COR000001",
                "merchantCode": "M000009",
                "title": "PDS蓝球",
                "content": "xxx",
                "price": "",
                "image": "2.jpg",
                "categoryCode": "CTM000001",
                "status": 10,
                "type": 10,
                "createdAt": "2018-12-27 16:32:48",
                "updatedAt": "2018-12-27 16:32:48",
                "section": "8"
            },
            {
                "id": 8,
                "code": "COR000004",
                "merchantCode": "M000009",
                "title": "PDS蓝球e",
                "content": "x66xx",
                "price": "100.00",
                "image": "1.jpg",
                "categoryCode": "CTM000001",
                "status": 10,
                "type": 10,
                "createdAt": "2019-01-02 15:57:52",
                "updatedAt": "2019-01-02 15:57:52",
                "section": "8"
            }
        ],
        "currentPage": 1,
        "total": 2,
        "perPage": "10",
        "lastPage": 1
    }
}
```


## 1.4.体验课预约 {#exprience-course-booking}
### 请求路径
`GET /api/exprience-course-booking`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|课程分类code  地址栏携带|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|title|body|string|Y|课程标题|
|image|body|string|Y|图片链接|

### 返回示例
```json
{
    "request": "7c9118dd-122c-406c-a947-3b8459a604a3",
    "code": 0,
    "message": "request_handle_successful",
    "data": {
        "data": [
            {
                "id": 8,
                "code": "COR000004",
                "merchantCode": "M000009",
                "title": "PDS蓝球e",
                "image": "1.jpg",
                "categoryCode": "CTM000001",
                "status": 10,
                "type": 20,
                "createdAt": "2019-01-02 15:57:52",
                "updatedAt": "2019-01-02 15:57:52",
                "section": "8"
            }
        ],
        "currentPage": 1,
        "total": 1,
        "perPage": "10",
        "lastPage": 1
    }
}
```
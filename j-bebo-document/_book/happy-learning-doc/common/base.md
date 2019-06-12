#公共模块
## 获取OPENID {#authorize}
### 请求路径
`GET /api/authorize`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|code|body|string|Y|微信登陆code|
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|openid|body|string|Y|openid|
|session_key|body|string|Y|session_key|
### 返回示例
```json
{
    "openid": "oxkfq0NMYybphA3O6ZvN585ZuJCI",
    "session_key": "RKt9WSMWs8ijJ6TVj4OBbQ=="
}
```



##保存学员信息 {#saveuserinfo}
###请求路径
`POST /api/saveuserinfo`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|iv|body|string|Y|iv|
|encryptedData|body|string|Y|encryptedData|
|sessionKey|body|string|Y|sessionKey|
### 请求示例
无
### 返回参数
无
### 返回示例
```json

```

##检查是否关注公众号 {#check-openid}
###请求路径
`GET /api/check-openid`
### 请求参数
无
### 请求示例
无
### 返回参数
无
### 返回示例
```json

```

## 文件上传 {#upload}
###请求参数
`POST /upload`
### 请求参数
无
### 请求示例
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|url|body|string|Y|地址|
|filename|body|string|Y|文件名|
### 返回示例

```json

```



## 省 {#public-province}
### 请求路径
`GET /public/province`
### 请求参数
无
### 请求示例
无
### 返回参数
无
### 返回示例

```json

```

## 市 {#public-city}
### 请求路径
`GET /public/city`
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


## 区 {#public-district}
### 请求路径
`GET /public/district`
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


## 分类获取 {#public-category}
### 请求路径
`GET /public/category`
### 请求参数
无
### 请求示例
无
### 返回参数
无
### 返回示例

```json

```


## 期数获取 {#public-stage}
### 请求路径
`GET /public/stage`
### 请求参数
无
### 请求示例
无
### 返回参数
无
### 返回示例

```json

```


## 级别获取 {#public-level}
### 请求路径
`GET /public/level`
### 请求参数
无
### 请求示例
无
### 返回参数
无
### 返回示例

```json

```

## 场地获取 {#public-field}
### 请求路径
`GET /public/field`
### 请求参数
无
### 请求示例
无
### 返回参数
无
### 返回示例

```json

```
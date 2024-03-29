# 1.用户模块
## 1.1.发送验证码 {#send-code}
### 请求路径
`POST /api/send-code`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|mobile|body|string|Y|手机号|
|type|body|int|Y|验证码类型 1登陆 2注册 3找回密码|
|captcha|body|string|N|type=2时，必传 注册时的图形验证码|
###正确返回示例

```json
{
    "status": 200,
    "message": "验证码已发送"
}
```
###错误返回示例

```json
{
    "status": 400,
    "message": "发送太过频繁，请稍后再试"
}
```
## 1.2.注册时的图形验证码 {#captcha}
### 请求路径
`GET /api/captcha`
### 请求参数
无
### 返回示例
```json

```

## 1.3.手机号注册 {#phone-register}
### 请求路径
`POST /api/phone-register`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|mobile|body|string|Y|手机号|
|password|body|string|Y|密码|
|confirm_password|body|string|Y|密码|
|code|body|string|Y|验证码|
###正确返回示例

```json
{
    "status": 200,
    "message": "登陆成功",
    "data": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJTSEEyNTYifQ.eyJpc3MiOiJTWSIsImlhdCI6MTU1OTM4MTg4NiwiZXhwIjoxNTU5OTg2Njg2LCJpZCI6Mywibmlja25hbWUiOiIiLCJhdmF0YXIiOiIiLCJzZXgiOjEsIm1vYmlsZSI6IjE4NjY1NzM2MzE1IiwicGFzc3dvcmQiOiJlMTBhZGMzOTQ5YmE1OWFiYmU1NmUwNTdmMjBmODgzZSIsInN0YXR1cyI6MSwiY3JlYXRlX3RpbWUiOiIyMDE5LTA2LTAxIDE2OjU2OjU5IiwidXBkYXRlX3RpbWUiOiIyMDE5LTA2LTAxIDE2OjU2OjU5In0.e860e36e43d0846ab86e3da07617e7b77f7babb2f53fe2afa9179a49f0d71fd7"
    }
}
```
###错误返回示例

```json
{
    "status": 400,
    "message": "该手机号已注册过，不可重复注册"
}
```
##1.4.手机号登陆 {#phone-login}
### 请求路径
`POST /api/phone-login`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|mobile|body|string|Y|手机号|
|password|body|string|Y|密码|
###返回示例

```json
{
    "status": 200,
    "message": "登陆成功",
    "data": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJTSEEyNTYifQ.eyJpc3MiOiJTWSIsImlhdCI6MTU1OTUyNTI3NCwiZXhwIjoxNTYwMTMwMDc0LCJpZCI6Mywibmlja25hbWUiOiIiLCJhdmF0YXIiOiIiLCJzZXgiOjEsIm1vYmlsZSI6IjE4NjY1NzM2MzE1IiwicGFzc3dvcmQiOiJlMTBhZGMzOTQ5YmE1OWFiYmU1NmUwNTdmMjBmODgzZSIsInN0YXR1cyI6MSwiY3JlYXRlX3RpbWUiOiIyMDE5LTA2LTAxIDE2OjU2OjU5IiwidXBkYXRlX3RpbWUiOiIyMDE5LTA2LTAxIDE2OjU2OjU5In0.656c414a67b675ea837e6b60d8e3e7ab6a32f0211714c549f9ebd7e0f6630331"
    }
}
```
##1.5.验证码登陆 {#code-login}
### 请求路径
`POST /api/code-login`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|mobile|body|string|Y|手机号|
|code|body|string|Y|验证码|
###返回示例

```json
{
    "status": 400,
    "message": "验证码已失效"
}
```

##1.6.找回密码 {#forget-pwd}
### 请求路径
`POST /api/forget-pwd`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|mobile|body|string|Y|手机号|
|password|body|string|Y|密码|
|confirm_password|body|string|Y|确认密码|
###返回示例

```json
{
    "status": 200,
    "message": "密码修改成功"
}
```



##1.7 设置登陆密码 {#setting-pwd}
### 请求路径
`POST /api/setting-pwd`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|old_password|body|string|Y|旧密码|
|new_password|body|string|Y|新密码|
|confirm_password|body|string|Y|确认密码|
###返回示例

```json
{
    "status": 200,
    "message": "设置密码成功"
}
```


##1.8 更改手机号 {#replace-phone}
### 请求路径
`POST /api/replace-phone`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|mobile|body|string|Y|旧密码|
|mobile|body|string|Y|新密码|
###返回示例

```json
{
    "status": 200,
    "message": "更改手机号成功"
}
```

##1.9 在线留言 {#save-message}
### 请求路径
`POST /api/save-message`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|name|body|string|N|姓名|
|mobile|body|string|Y|手机号|
|email|body|string|N|邮箱|
|address|body|string|N|地址|
###返回示例

```json
{
    "status": 200,
    "message": "留言成功"
}
```


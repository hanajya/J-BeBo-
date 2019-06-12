# 项目基本信息 {#about}

本项目主要分为四端。两个小程序、两个PC管理后台。主要技术框架要求：
* 总后台框架要求 [Laravel 5.7](https://laravelacademy.org/laravel-docs-5_7)
* 商家后台框架要求 [Laravel 5.7](https://laravelacademy.org/laravel-docs-5_7)
* PC后台框架要求 [Vue-element-admin](https://github.com/PanJiaChen/vue-element-admin/blob/master/README.zh-CN.md)
* 小程序框架要求 [mpvue](https://github.com/Meituan-Dianping/mpvue)

项目代码存放在gitlab上面的仓库,本项目使用的第三方一些库

* 文件存储服务 [minio](https://github.com/minio/minio),测试环境相关信息参考gitlab文档项目的wiki内容.
* 前端上传文件到minio可以参考此[文档](https://docs.minio.io/docs/upload-files-from-browser-using-pre-signed-urls.html).
* 后端生成前端上传用的`pre-signed URLs`可以直接安装[PHP版AWS SDK](https://github.com/aws/aws-sdk-php),然后直接调用里面的`Aws\S3\S3Client`类的`createPresignedRequest`方法尝试一下。

# 请求方式 {#request-method}

### 统一的返回格式

```json
{
    "code":0,
    "message":"错误信息/handle successful.",
    "data":{
        "name":"xxxx"
    }
}
```

```json
{
    "code":0,
    "message":"错误信息/handle successful.",
    "data":[
        {
            "name":"xxx1"
        },
        {
            "name":"xxx2"
        }
    ]
}
```

```json
{
    "code":0,
    "message":"handle successful.",
    "data":[]
}
```


# 签名算法 {#signature-algorithm}

# 错误代码表 {#error-code-table}

# Introduction


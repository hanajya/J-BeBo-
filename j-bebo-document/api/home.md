#2.首页模块
### 2.1.首页选项卡 {#tabs}
### 请求路径
`GET /api/tabs`
### 请求参数
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|jube|body|int|Y|聚宝积分|
|fold_au|body|int|Y|折上折金币|
|fold_ag|body|int|Y|折上折银币|
|fold_cu|body|int|Y|折上折铜币|
|modules.id|body|int|Y|选项ID|
|modules.module_name|body|string|Y|选项名称|
###返回示例
```json
{
    "status": 200,
    "message": "",
    "data": {
        "jube": 0,
        "fold_au": {
            "type": 1,
            "num": 0
        },
        "fold_ag": {
            "type": 2,
            "num": 0
        },
        "fold_cu": {
            "type": 3,
            "num": 0
        },
        "modules": [
            {
                "id": 1,
                "module_name": "聚宝",
                "status": 1,
                "create_time": null,
                "update_time": null
            },
            {
                "id": 2,
                "module_name": "折上折",
                "status": 1,
                "create_time": null,
                "update_time": null
            }
        ]
    }
}
```

### 2.2.商品列表 {#goods-list}
### 请求路径
`GET /api/goods-list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|keyword|body|string|N|搜索关键词|
|module_id|body|int|Y|模块ID 1聚宝 2 折上折|
|page|body|int|Y|页数|
|limit|body|int|Y|条数|
|sort|body|int|Y|排序 1综合 2销量 3价格 默认1|
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|goods_id|body|int|Y|商品ID|
|goods_name|body|int|Y|商品名称|
|module_id|body|int|Y|模块ID 1聚宝 2折上折|
|points|body|string/array|Y|模块ID=1时是积分参数，=2时是数组形式包括coin_type(1为金币，2为银币，3为铜币),coins数量|
|sale_price|body|decimal|Y|销售价格|
|stock|body|int|Y|现货|
|sales_num|body|int|Y|已售数量|
|evaluates_num|body|int|Y|评价数量|
|type_id|body|int|Y|1 正常商品 2限时抢新商品|
|loot_start|body|int|Y|当type_id =2 时，限时抢新商品的开始时间|
|loot_end|body|int|Y|当type_id =2 时，限时抢新商品的结束时间|
|img|body|int|Y|当type_id =1 时，首图|
|goods_img_arr|body|int|Y|当type_id =2 时，数组形式|
###返回示例
```json
{
    "status": 200,
    "message": [
        {
            "goods_id": 2,
            "goods_name": "Emporio Armani 2019春夏黑白色通体爱心印花女士连衣裙",
            "module_id": 1,
            "points": "1680",
            "sale_price": "1680.00",
            "stock": 200,
            "sales_num": 80,
            "evaluates_num": 11,
            "type_id": 1,
            "loot_start": 0,
            "loot_end": 1559797878,
            "img": "",
            "goods_img_arr": null
        },
        {
            "goods_id": 1,
            "goods_name": "兰蔻美白面霜 ",
            "module_id": 1,
            "points": "1000",
            "sale_price": "1000.00",
            "stock": 1000,
            "sales_num": 200,
            "evaluates_num": "99+",
            "type_id": 1,
            "loot_start": 0,
            "loot_end": 0,
            "img": "",
            "goods_img_arr": null
        }
    ]
}
```

### 2.3.商品详情 {#goods-detail}
### 请求路径
`GET /api/goods-detail`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|goods_id|header|int|Y|商品ID|
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|goods_id|body|int|Y|商品ID|
|goods_name|body|int|Y|商品名称|
|module_id|body|int|Y|模块ID 1聚宝 2折上折|
|points|body|string/array|Y|模块ID=1时是积分参数，=2时是数组形式包括coin_type(1为金币，2为银币，3为铜币),coins数量|
|sale_price|body|decimal|Y|销售价格|
|stock|body|int|Y|现货|
|sales_num|body|int|Y|已售数量|
|evaluates_num|body|int|Y|评价数量|
|type_id|body|int|Y|1 正常商品 2限时抢新商品|
|loot_start|body|int|Y|当type_id =2 时，限时抢新商品的开始时间|
|loot_end|body|int|Y|当type_id =2 时，限时抢新商品的结束时间|
|goods_img_arr|body|int|Y|当type_id =2 时，数组形式|
|evaluates|body|array|Y|当evaluates是数组时，有评论|
|evaluates.content|body|string|Y|评论内容|
|evaluates.buyer_id|body|int|Y|用户ID|
|evaluates.goods_id|body|int|Y|商品ID|
|evaluates.goods_imgs|body|int|Y|商品图片|
|evaluates.buyer_name|body|string|Y|用户名|
|evaluates.is_anonymous|body|int|Y|是否匿名|
|evaluates.addtime|body|int|Y|评论时间|
###返回示例
```json
{
    "status": 200,
    "message": {
        "goods_id": 3,
        "goods_name": "2019春夏新款专柜正品牌女装阿玛尼连衣裙代购真丝印花宽松中长",
        "module_id": 2,
        "points": {
            "coin_type": "1",
            "coins": "528"
        },
        "sale_price": "1000.00",
        "stock": 100,
        "sales_num": 100,
        "evaluates_num": 50,
        "type_id": 1,
        "goods_img_arr": "['https://gd1.alicdn.com/imgextra/i1/1615730789/O1CN01cgvoUG1HhOzsco0Sh_!!1615730789.jpg_400x400.jpg']",
        "evaluates": null,
        "evaluates": {
            "content": "好野好平",
            "buyer_id": 10,
            "goods_id": 1,
            "goods_imgs": "",
            "buyer_name": "1***5736315",
            "is_anonymous": 0,
            "addtime": 1559797878,
            "buyer_avatar": "https://ss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=2403757908,2884150216&fm=58&bpow=518&bpoh=619"
        }
    }
}
```

### 2.4.积分或币种的流水记录 {#account-record} 未完成-缺少设计图
### 请求路径
`GET /api/account-record`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|module_id|header|int|Y|模块ID|
|type|header|int|Y|类型 聚宝传0|
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
###返回示例
```json
{
    "status": 200,
    "message": "",
    "data": []
}
```







































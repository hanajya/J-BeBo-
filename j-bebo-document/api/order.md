#4.订单模块
### 4.1.订单确认页 {#confirm-order}
### 请求路径
`POST /api/confirm-order`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|sku_arr.sku_id|body|array|Y|单个或多个sku_id|
|sku_arr.num|body|array|Y|单个可多个商品数量|
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|address_arr|body|array|Y|用户地址|
|goods_arr.content|body|array|Y|多商家商品信息|
|goods_arr.content.single_price|body|int|Y|单件商品价格|
|goods_arr.content.single_coins|body|int|Y|单件商品积分或币种|
|goods_arr.merchant_price|body|int|Y|一个商家下的所有商品价格|
|goods_arr.express_total_fee|body|int|Y|一个商家下的所有商品运费|
|goods_arr.merchant_coins_spec|body|array|Y|一个商家下的所有商品的积分或币，及币的类型|
|total_arr|body|array|Y|所有商家下的所有商品的积分或币，及币的类型 及商品价格|
### 参数传递示例 
```json
"sku_arr":[{
        "sku_id":1,
        "num":2
    },{
        "sku_id":2,
        "num":1
    },{

        "sku_id":3,
        "num":2
    },{
        "sku_id":4,
        "num":1
}]
```
###返回示例
```json
{
    "status": 200,
    "message": "",
    "data": {
        "address_arr": [],
        "goods_arr": [
            {
                "content": [
                    {
                        "module_id": 2,
                        "goods_name": "兰蔻美白面霜 ",
                        "sku_name": "温和型",
                        "single_price": 2000,
                        "single_coins": 2000,
                        "sale_price": "1000.00",
                        "points": {
                            "coin_type": "2",
                            "coins": "1000"
                        },
                        "img": "https://img.alicdn.com/imgextra/i4/2360209412/O1CN01JSNKx32JOkIvpHJsF_!!0-item_pic.jpg_430x430q90.jpg",
                        "payType": "线上支付",
                        "num": 2,
                        "express_fee": 2002
                    },
                    {
                        "module_id": 2,
                        "goods_name": "2019春夏新款专柜正品牌女装阿玛尼连衣裙代购真丝印花宽松中长",
                        "sku_name": "",
                        "single_price": 1000,
                        "single_coins": 528,
                        "sale_price": "1000.00",
                        "points": {
                            "coin_type": "1",
                            "coins": "528"
                        },
                        "img": "https://gd1.alicdn.com/imgextra/i1/1615730789/O1CN01cgvoUG1HhOzsco0Sh_!!1615730789.jpg_400x400.jpg",
                        "payType": "线上支付",
                        "num": 1,
                        "express_fee": "0.00"
                    },
                    {
                        "module_id": 2,
                        "goods_name": "兰蔻美白面霜 ",
                        "sku_name": "清爽型",
                        "single_price": 2000,
                        "single_coins": 2000,
                        "sale_price": "1000.00",
                        "points": {
                            "coin_type": "2",
                            "coins": "1000"
                        },
                        "img": "https://img.alicdn.com/imgextra/i4/2360209412/O1CN01JSNKx32JOkIvpHJsF_!!0-item_pic.jpg_430x430q90.jpg",
                        "payType": "线上支付",
                        "num": 2,
                        "express_fee": 2002
                    }
                ],
                "module_id": 2,
                "goods_id": 1,
                "express_total_fee": 4004,
                "merchant_price": 5000,
                "merchant_coins_spec": [
                    {
                        "coin_type": "1",
                        "coins": 528
                    },
                    {
                        "coin_type": "2",
                        "coins": 4000
                    }
                ]
            }
        ],
        "total_arr": {
            "total_sale_price": 9004,
            "total_coins_spec": [
                {
                    "coin_type": "1",
                    "coins": 528
                },
                {
                    "coin_type": "2",
                    "coins": 4000
                }
            ]
        }
    }
}
```

### 4.2.创建订单 {#create-order}
### 请求路径
`POST /api/create-order`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|sku_arr.sku_id|body|array|Y|单个或多个sku_id|
|sku_arr.num|body|array|Y|单个可多个商品数量|
|address_id|body|int|Y|地址ID|
### 返回参数
无
### 参数传递示例 
```json
"sku_arr":[{
        "sku_id":1,
        "num":2
    },{
        "sku_id":2,
        "num":1
    },{

        "sku_id":3,
        "num":2
    },{
        "sku_id":4,
        "num":1
}]
"address_id":1
```

###返回示例
```json
{
    "status": 200,
    "message": "",
}
```

### 4.3.我的订单列表【未完成】 {#order-list}
### 请求路径
`GET /api/order-list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|order_status|body|int|Y|用户端订单状态 未支付0 已支付1,2,3 已完成4|
### 返回参数

### 返回示例




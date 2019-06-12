#3.购物车
### 3.1.加入购物车 {#add-cart}
### 请求路径
`POST /api/add-cart`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|sku_id|header|int|Y|skuID|
|num|header|int|Y|商品数量|
### 返回参数
无
###返回示例
```json
{
	"status":200,
	"message":"加入购物车成功"
}
```

### 3.2.购物车列表 {#cart-list}
### 请求路径
`GET /api/cart-list`
### 请求参数
无
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|goods_id|body|int|Y|goodsID|
|sku_id|body|int|Y|skuID|
|user_id|body|int|Y|用户ID|
|merchant_id|body|int|Y|商户ID|
|module_id|body|int|Y|模块ID 1聚宝 2折上折|
|goods_name|body|string|Y|商品名|
|sku_name|body|string|Y|规格名 没有则无规格|
|points|body|string/array|Y|模块ID=1时是积分参数，=2时是数组形式包括coin_type(1为金币，2为银币，3为铜币),coins数量|
|price|body|decimal|Y|价格|
|num|body|int|Y|数量|
|goods_img|body|string|Y|图片|
|goods_type|body|int|Y|商品类型 1 正常商品 2限时抢新商品|
|status|body|int|Y|商品状态 1 正常 2过期 0 下架|
### 返回示例
```json
{
    "status": 200,
    "message": "",
    "data": [
        {
            "goods_id": 1,
            "sku_id": 1,
            "user_id": 9,
            "merchant_id": 1,
            "module_id": 1,
            "goods_name": "兰蔻美白面霜 ",
            "sku_name": "温和型",
            "points": "1000",
            "price": "1000.00",
            "num": 1,
            "goods_img": "https://img.alicdn.com/imgextra/i4/2360209412/O1CN01JSNKx32JOkIvpHJsF_!!0-item_pic.jpg_430x430q90.jpg",
            "goods_type": 1,
            "status": 1
        },
        {
            "goods_id": 1,
            "sku_id": 2,
            "user_id": 9,
            "merchant_id": 1,
            "module_id": 1,
            "goods_name": "兰蔻美白面霜 ",
            "sku_name": "清爽型",
            "points": "1000",
            "price": "1000.00",
            "num": 1,
            "goods_img": "https://img.alicdn.com/imgextra/i4/2360209412/O1CN01JSNKx32JOkIvpHJsF_!!0-item_pic.jpg_430x430q90.jpg",
            "goods_type": 1,
            "status": 1
        },
        {
            "goods_id": 2,
            "sku_id": 3,
            "user_id": 9,
            "merchant_id": 1,
            "module_id": 1,
            "goods_name": "Emporio Armani 2019春夏黑白色通体爱心印花女士连衣裙",
            "sku_name": "",
            "points": "1680",
            "price": "1680.00",
            "num": 2,
            "goods_img": "https://img.alicdn.com/imgextra/i1/3793607024/O1CN01Z2ZkDG21l2TsbnS0J_!!3793607024.jpg_430x430q90.jpg",
            "goods_type": 2,
            "status": 2
        },
        {
            "goods_id": 3,
            "sku_id": 4,
            "user_id": 9,
            "merchant_id": 1,
            "module_id": 2,
            "goods_name": "2019春夏新款专柜正品牌女装阿玛尼连衣裙代购真丝印花宽松中长",
            "sku_name": "",
            "points": {
                "coin_type": "1",
                "coins": "528"
            },
            "price": "1000.00",
            "num": 1,
            "goods_img": "https://gd1.alicdn.com/imgextra/i1/1615730789/O1CN01cgvoUG1HhOzsco0Sh_!!1615730789.jpg_400x400.jpg",
            "goods_type": 1,
            "status": 1
        }
    ]
}
```

### 3.3.删除购物车 {#del-cart}
### 请求路径
`POST /api/del-cart`
### 请求参数
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|sku_id|header|int|Y|skuID|
### 返回参数
无
### 返回示例
```json
{
    "status":200,
    "message":"删除成功"
}
```

### 3.4.商品数量增减 {#num-change}
### 请求路径
`POST /api/num-change`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|goods_id|body|int|Y|goodsID|
|sku_id|body|int|Y|skuID|
|number|body|string|Y|增加时传正数，减少时传负数 如 -1|
### 返回参数
无
### 返回示例
```json
{
    "status":200,
    "message":"修改成功"
}
```
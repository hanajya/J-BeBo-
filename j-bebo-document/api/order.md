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

### 4.3.我的订单列表 {#order-list}
### 请求路径
`GET /api/order-list`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|order_status|body|int|Y|用户端订单状态 全部all 未支付0 已支付1,2,3 已完成4|
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|order_id|body|int|Y|订单号|
|order_no|body|string|Y|订单编号|
|out_trade_no|body|string|Y|外部交易号|
|order_type|body|string|Y|订单类型 1 正常商品 2限时抢新|
|pay_type|body|int|Y|支付类型 1线上支付|
|buyer_id|body|int|Y|用户编号|
|buyer_name|body|string|Y|用户昵称|
|buyer_message|body|string|Y|卖家留言|
|receiver_mobile|body|string|Y|收货人电话|
|receiver_name|body|string|Y|收货人姓名|
|receiver_province|body|string|Y|省|
|receiver_city|body|string|Y|市|
|receiver_district|body|string|Y|区|
|receiver_address|body|string|Y|详细地址|
|order_price|body|int|Y|订单总价|
|points_attr|body|int|Y|积分|
|shipping_company_id|body|int|Y|配送物流ID|
|shipping_money|body|int|Y|运费|
|pay_money|body|int|Y|实付金额|
|refund_money|body|int|Y|退款金额|
|order_status|body|int|Y|订单状态 0待支付 1待发货 2已发货 3已收货 4 已完成 5 已关闭 -1退款中 -2已退款|
|pay_status|body|int|Y|支付状态 0未支付 1已支付|
|pay_time|body|int|Y|支付时间|
|sign_time|body|int|Y|买家签收时间|
|consign_time|body|int|Y|卖家发货时间|
|create_time|body|int|Y|创建时间|
|order_goods|body|array|Y|订单商品|
|order_goods.order_id|body|int|Y|订单号|
|order_goods.goods_id|body|int|Y|商品编号|
|order_goods.goods_name|body|string|Y|商品名称|
|order_goods.sku_id|body|int|Y|SKU编号|
|order_goods.sku_name|body|string|Y|SKU名称|
|order_goods.price|body|int|Y|销售价|
|order_goods.buy_num|body|int|Y|购买数量|
|order_goods.goods_money|body|int|Y|商品总价|
|order_goods.goods_img|body|string|Y|商品图片|
|order_goods.module_id|body|int|Y|模块ID|
|order_goods.merchant_id|body|int|Y|商户ID|
|order_goods.points|body|int|Y|积分|
|order_goods.coin_type|body|int|Y|币类型 1金2银3铜|
|order_goods.coins|body|int|Y|币数量
|order_goods.goods_type|body|int|Y|商品类型 1正常商品 2限时抢新|
### 返回示例
{
	"status": 200,
	"message": "",
	"data": [{
		"order_id": 3,
		"order_no": "1906141744007665",
		"out_trade_no": "",
		"order_type": "[1]",
		"pay_type": 1,
		"buyer_id": 12,
		"buyer_name": "18665736315",
		"buyer_message": "",
		"receiver_mobile": "18665736315",
		"receiver_name": "syuka",
		"receiver_province": "广东省",
		"receiver_city": "深圳市",
		"receiver_district": "宝安区",
		"receiver_address": "九树墩20号",
		"order_price": "7002.00",
		"points_attr": "{\"2\":{\"type\":\"2\",\"coins\":2000},\"3\":{\"type\":\"3\",\"coins\":1584}}",
		"shipping_company_id": 0,
		"shipping_money": "2002.00",
		"pay_money": "7002.00",
		"refund_money": "0.00",
		"order_status": 0,
		"pay_status": 0,
		"pay_time": 0,
		"sign_time": 0,
		"consign_time": 0,
		"create_time": "2019-06-14 17:44:00",
		"order_goods": [{
			"order_id": 3,
			"goods_id": 1,
			"goods_name": "兰蔻美白面霜 ",
			"sku_id": 2,
			"sku_name": "清爽型",
			"price": "1000.00",
			"buy_num": "2",
			"goods_money": "2000.00",
			"goods_img": "",
			"module_id": 2,
			"merchant_id": 2,
			"points": "0",
			"coin_type": 2,
			"coins": 2,
			"goods_type": 1
		}, {
			"order_id": 3,
			"goods_id": 3,
			"goods_name": "2019春夏新款专柜正品牌女装阿玛尼连衣裙代购真丝印花宽松中长",
			"sku_id": 4,
			"sku_name": null,
			"price": "1000.00",
			"buy_num": "3",
			"goods_money": "3000.00",
			"goods_img": "",
			"module_id": 2,
			"merchant_id": 2,
			"points": "0",
			"coin_type": 3,
			"goods_type": 1
		}]
	}]
}

### 4.4.我的订单详情 {#order-detail}
### 请求路径
`GET /api/order-detail/4`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|order_id|body|int|Y|订单状态|
### 返回参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|order_id|body|int|Y|订单号|
|order_no|body|string|Y|订单编号|
|out_trade_no|body|string|Y|外部交易号|
|order_type|body|string|Y|订单类型 1 正常商品 2限时抢新|
|pay_type|body|int|Y|支付类型 1线上支付|
|buyer_id|body|int|Y|用户编号|
|buyer_name|body|string|Y|用户昵称|
|buyer_message|body|string|Y|卖家留言|
|receiver_mobile|body|string|Y|收货人电话|
|receiver_name|body|string|Y|收货人姓名|
|receiver_province|body|string|Y|省|
|receiver_city|body|string|Y|市|
|receiver_district|body|string|Y|区|
|receiver_address|body|string|Y|详细地址|
|order_price|body|int|Y|订单总价|
|points_attr|body|int|Y|积分|
|shipping_company_id|body|int|Y|配送物流ID|
|shipping_money|body|int|Y|运费|
|pay_money|body|int|Y|实付金额|
|refund_money|body|int|Y|退款金额|
|order_status|body|int|Y|订单状态 0待支付 1待发货 2已发货 3已收货 4 已完成 5 已关闭 -1退款中 -2已退款|
|pay_status|body|int|Y|支付状态 0未支付 1已支付|
|pay_time|body|int|Y|支付时间|
|sign_time|body|int|Y|买家签收时间|
|consign_time|body|int|Y|卖家发货时间|
|create_time|body|int|Y|创建时间|
|order_goods|body|array|Y|订单商品|
|order_goods.order_id|body|int|Y|订单号|
|order_goods.goods_id|body|int|Y|商品编号|
|order_goods.goods_name|body|string|Y|商品名称|
|order_goods.sku_id|body|int|Y|SKU编号|
|order_goods.sku_name|body|string|Y|SKU名称|
|order_goods.price|body|int|Y|销售价|
|order_goods.buy_num|body|int|Y|购买数量|
|order_goods.goods_money|body|int|Y|商品总价|
|order_goods.goods_img|body|string|Y|商品图片|
|order_goods.module_id|body|int|Y|模块ID|
|order_goods.merchant_id|body|int|Y|商户ID|
|order_goods.points|body|int|Y|积分|
|order_goods.coin_type|body|int|Y|币类型 1金2银3铜|
|order_goods.coins|body|int|Y|币数量
|order_goods.goods_type|body|int|Y|商品类型 1正常商品 2限时抢新|
### 返回示例
```json
{
	"status": 200,
	"message": {
		"order_id": 1,
		"order_no": "1906141451325137",
		"out_trade_no": "",
		"order_type": "[1]",
		"pay_type": 1,
		"buyer_id": 10,
		"buyer_name": "18665736315",
		"buyer_message": "",
		"receiver_mobile": "18665736315",
		"receiver_name": "syuka",
		"receiver_province": "广东省",
		"receiver_city": "深圳市",
		"receiver_district": "宝安区",
		"receiver_address": "九树墩20号",
		"order_price": "5002.00",
		"points_attr": "{\"2\":{\"type\":\"2\",\"coins\":2000},\"3\":{\"type\":\"3\",\"coins\":528}}",
		"shipping_company_id": 0,
		"shipping_money": "2002.00",
		"pay_money": "5002.00",
		"refund_money": "0.00",
		"order_status": 0,
		"pay_status": 0,
		"pay_time": 0,
		"sign_time": 0,
		"consign_time": 0,
		"create_time": "2019-06-14 14:51:33",
		"order_goods": [{
			"order_id": 1,
			"goods_id": 1,
			"goods_name": "兰蔻美白面霜 ",
			"sku_id": 1,
			"sku_name": "温和型",
			"price": "1000.00",
			"buy_num": "2",
			"goods_money": "2000.00",
			"goods_img": "",
			"module_id": 2,
			"merchant_id": 2,
			"points": "0",
			"coin_type": 2,
			"goods_type": 1
		}, {
			"order_id": 1,
			"goods_id": 3,
			"goods_name": "2019春夏新款专柜正品牌女装阿玛尼连衣裙代购真丝印花宽松中长",
			"sku_id": 4,
			"sku_name": null,
			"price": "1000.00",
			"buy_num": "1",
			"goods_money": "1000.00",
			"goods_img": "",
			"module_id": 2,
			"merchant_id": 2,
			"points": "0",
			"coin_type": 3,
			"goods_type": 1
		}]
	}
}
```
### 4.5.用户取消订单{#cancel-order}
### 请求路径
`POST /api/cancel-order`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|order_id|body|int|Y|订单编号
### 返回参数
无
### 返回示例
```json
{
    "status": 200,
    "message": "取消成功"
}
```

### 4.6.用户确认订单{#complete-order}
### 请求路径
`POST /api/complete-order`
### 请求参数
|参数名|位置|类型|必须|说明|
|:----:|:----:|:----:|:----:|:-------:|
|order_id|body|int|Y|订单编号
### 返回参数
无
### 返回示例
```json
{
    "status": 200,
    "message": "确认成功"
}
```
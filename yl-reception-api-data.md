```
http://127.0.0.1:9999/zuul/dr-frame-auth/sysUser/getVerificationCode
{"phone":15202881231}

http://127.0.0.1:9999/zuul/dr-frame-auth/sysUser/registerAppUser
{"phone":15202881231,"verCode":"38274"}


http://127.0.0.1:9999/zuul/dr-frame-auth/login/app
{"phone":15202881231,"verCode":}

http://127.0.0.1:9999/zuul/reception-api-cfg/indexBanner/getList
{"shopId":100}

http://127.0.0.1:9999/zuul/reception-api-comm/category/getList
{}

http://127.0.0.1:9999/zuul/reception-api-comm/spu/getHotSaleSpuList
{}

http://127.0.0.1:9999/zuul/reception-api-comm/spu/getRecommendSpuList
{}


http://127.0.0.1:9999/zuul/reception-api-shop/hotSearch/getList
{}

http://127.0.0.1:9999/zuul/reception-api-comm/spu/getAllSpuList
{}

http://127.0.0.1:9999/zuul/reception-api-comm/spu/findById
{"id":100}

http://127.0.0.1:9999/zuul/reception-api-comm/shopCartItem/selectPage
{"userId":100}

http://127.0.0.1:9999/zuul/reception-api-comm/shopCartItem/addShopCartItem
{"shopId":100,"spuId":100,"skuId":100,"userId":100,"count":5,"priceFee":10.6}

http://127.0.0.1:9999/zuul/reception-api-comm/shopCartItem/reduceShopCartItem
{"shopId":100,"spuId":100,"skuId":100,"userId":100,"count":1,"priceFee":10.6}

http://127.0.0.1:9999/zuul/reception-api-app-user/userGoodFriend/getUserGoodFriendList
{"userId":117,"status":1}

http://127.0.0.1:9999/zuul/reception-api-app-user/userGoodFriendApply/addGoodFriendApply
{"userId":117,"content":"测试","remarks":"小哥"}

http://127.0.0.1:9999/zuul/reception-api-app-user/userGoodFriendApply/getNewGoogFriendList
{}


创建钱包
{"name":"马勤书","idCardType":"500240199308251617","mobile":"15202881231","profession":"A",
	"mac":"00:00:00:00:00:00",
	"nickName":"测试",
	"sysUser":{"id":124}
}


```

```java
SysUser sysUser = null;
		try {
			sysUser = JSONObject.parseObject(JSONObject.toJSONString(param.get("sysUser")), SysUser.class);
		} catch (Exception e) {
			return new RetResult(RetCode.ERRO.getCode(), "请先登录！");
		}
		


键名首字母排序
SHA1 签名
CFCA 私钥签名
AES 加密
CFCA 公钥加密
		
		
```


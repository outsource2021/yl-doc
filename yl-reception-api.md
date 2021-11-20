## APP

| 版本号 | 修改人 | 修改日期   | 修改说明 |
| ------ | ------ | ---------- | -------- |
| v1.0   | 马勤书 | 2021.10.25 |          |

### 请求头

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| token    | string   | 是       | 令牌     |

### 1.授权码获取

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/dr-frame-auth/auth/getAuthCode

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          |          |          | header   |
| token    | String   | 是       | token    |

**返回参数：**

| 参数名称  | 参数类型 | 是否必须 | 参数说明 |
| --------- | -------- | -------- | -------- |
| auth_code | String   | 是       | 授权码   |

### 2.注册

#### 2.1.获取验证码

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/dr-frame-auth/sysUser/getVerificationCode

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                             |
| -------- | -------- | -------- | ------------------------------------ |
| type     | Int      | 是       | 短信类型（1.注册 2.登录 3.修改密码） |
| phone    | Long     | 是       | 电话号码                             |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 2.2.注册

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/dr-frame-auth/sysUser/registerAppUser

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明   |
| -------- | -------- | -------- | ---------- |
| phone    | Long     | 是       | 电话号码   |
| verCode  | String   | 是       | 短信验证码 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 3.登录

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/dr-frame-auth/login/app

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| phone    | Long     | 是       | 电话     |
| password | String   | 否       | 密码     |
| verCode  | String   | 否       | 验证码   |

**返回参数：**

| 参数名称          | 参数类型 | 是否必须 | 参数说明                                                     |
| ----------------- | -------- | -------- | ------------------------------------------------------------ |
| id                | Long     | 是       | 用户ID                                                       |
| phone             | String   | 是       | 用户名                                                       |
| token             | String   | 是       | token                                                        |
| nickname          | String   | 是       | 用户昵称                                                     |
| headimgurl        | String   | 是       | 头像地址                                                     |
| qrUrl             | String   | 是       | 二维码                                                       |
| sex               | Int      | 是       | 用户的性别，值为1时是男性<br />，值为2时是女性，<br />值为0时是未知 |
| imAccount         | String   | 是       | im账号                                                       |
| imPassword        | String   | 是       | 密码                                                         |
| isVip             | Boolean  | 是       | 是否会员                                                     |
| vipExpirationTime | String   | 是       | 会员到期时间                                                 |
| walletId          | String   | 是       | 钱包 ID                                                      |
| yAccount          | String   | 是       | 域号                                                         |

### 4.首页

#### 4.1.banner列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-cfg/indexBanner/getList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| shopId   | Long     | 否       | 店铺ID   |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                 |
| ---------- | -------- | -------- | ------------------------ |
| id         | Long     | 是       | id                       |
| shopId     | Long     | 是       | 店铺ID                   |
| imgUrl     | String   | 是       | 图片                     |
| des        | String   | 是       | 文字说明                 |
| title      | String   | 是       | 标题                     |
| link       | String   | 是       | 链接                     |
| status     | Int      | 是       | 状态                     |
| seq        | Int      | 是       | 排序                     |
| relation   | Long     | 是       | 关联                     |
| type       | Int      | 是       | 类型（1、平台  2、店铺） |
| createTime | String   | 是       | 添加时间                 |
| updateTime | String   | 是       | 更新时间                 |

#### 4.2.分类列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-comm/category/getList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| parentId | Long     | 否       | 父级ID   |
| shopId   | Long     | 否       | 店铺ID   |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                             |
| ---------- | -------- | -------- | ------------------------------------ |
| id         | Long     | 是       | 分类id                               |
| parentId   | Long     | 是       | 父ID                                 |
| name       | String   | 是       | 分类名称                             |
| desc       | String   | 是       | 分类描述                             |
| path       | String   | 是       | 分类地址{parent_id}-{child_id},...   |
| status     | Int      | 是       | 状态 1:enable, 0:disable, -1:deleted |
| icon       | String   | 是       | 分类图标                             |
| imgUrl     | String   | 是       | 分类的显示图片                       |
| level      | Int      | 是       | 分类层级 从0开始                     |
| seq        | Int      | 是       | 排序                                 |
| createTime | String   | 是       | 添加时间                             |
| updateTime | String   | 是       | 更新时间                             |

#### 4.3.热销商品列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-comm/spu/getHotSaleSpuList

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |

**返回参数：**

| 参数名称       | 参数类型 | 是否必须 | 参数说明                  |
| -------------- | -------- | -------- | ------------------------- |
| pages          | Int      | 是       | 总页数                    |
| total          | Int      | 是       | 总条数                    |
| current        | Int      | 是       | 当前显示页                |
| size           | Int      | 是       | 每页显示条数              |
| records        | List     | 是       | 数据列表                  |
|                |          |          | records                   |
| id             | Long     | 是       | spu id                    |
| shopId         | Long     | 是       | 店铺id                    |
| name           | String   | 是       | 商品名称                  |
| sellingPoint   | String   | 是       | 卖点                      |
| mainImgUrl     | String   | 是       | 商品介绍主图              |
| imgUrls        | String   | 是       | 商品图片 多个图片逗号分隔 |
| video          | String   | 是       | 商品视频                  |
| skuId          | Long     | 是       | 规格ID                    |
| saleNum        | Long     | 是       | 销量                      |
| skuPriceFee    | Double   | 是       | 规格售价                  |
| skuActualStock | Int      | 是       | 规格实际库存              |
| weight         | Double   | 是       | 商品重量                  |
| volume         | Double   | 是       | 商品体积                  |
| spuDetail      | Object   | 是       | 商品详情                  |

#### 4.4.推荐商品列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-comm/spu/getRecommendSpuList

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |

**返回参数：**

| 参数名称       | 参数类型 | 是否必须 | 参数说明                  |
| -------------- | -------- | -------- | ------------------------- |
| pages          | Int      | 是       | 总页数                    |
| total          | Int      | 是       | 总条数                    |
| current        | Int      | 是       | 当前显示页                |
| size           | Int      | 是       | 每页显示条数              |
| records        | List     | 是       | 数据列表                  |
|                |          |          | records                   |
| id             | Long     | 是       | spu id                    |
| shopId         | Long     | 是       | 店铺id                    |
| name           | String   | 是       | 商品名称                  |
| sellingPoint   | String   | 是       | 卖点                      |
| mainImgUrl     | String   | 是       | 商品介绍主图              |
| imgUrls        | String   | 是       | 商品图片 多个图片逗号分隔 |
| video          | String   | 是       | 商品视频                  |
| skuId          | Long     | 是       | 规格ID                    |
| saleNum        | Long     | 是       | 销量                      |
| skuPriceFee    | Double   | 是       | 规格售价                  |
| skuActualStock | Int      | 是       | 规格实际库存              |
| weight         | Double   | 是       | 商品重量                  |
| volume         | Double   | 是       | 商品体积                  |
| spuDetail      | Object   | 是       | 商品详情                  |

#### 4.5.热搜列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-shop/hotSearch/getList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明            |
| -------- | -------- | -------- | ------------------- |
| shopId   | Long     | 否       | 店铺ID（0平台热搜） |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明         |
| ---------- | -------- | -------- | ---------------- |
| id         | Long     | 是       | 热搜ID           |
| shopId     | Long     | 是       | 店铺ID           |
| title      | String   | 是       | 热搜标题         |
| content    | String   | 是       | 内容             |
| seq        | Int      | 是       | 排序             |
| status     | Int      | 是       | 状态 0下线 1上线 |
| createTime | String   | 是       | 添加时间         |
| updateTime | String   | 是       | 更新时间         |

### 5.商品

#### 5.1.商品列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-comm/spu/getAllSpuList

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |
| searchName  | String   | 否       | 搜索条件       |
| categoryId  | Long     | 否       | 分类ID         |

**返回参数：**

| 参数名称       | 参数类型 | 是否必须 | 参数说明                  |
| -------------- | -------- | -------- | ------------------------- |
| pages          | Int      | 是       | 总页数                    |
| total          | Int      | 是       | 总条数                    |
| current        | Int      | 是       | 当前显示页                |
| size           | Int      | 是       | 每页显示条数              |
| records        | List     | 是       | 数据列表                  |
|                |          |          | records                   |
| id             | Long     | 是       | spu id                    |
| shopId         | Long     | 是       | 店铺id                    |
| name           | String   | 是       | 商品名称                  |
| sellingPoint   | String   | 是       | 卖点                      |
| mainImgUrl     | String   | 是       | 商品介绍主图              |
| imgUrls        | String   | 是       | 商品图片 多个图片逗号分隔 |
| video          | String   | 是       | 商品视频                  |
| skuId          | Long     | 是       | 规格ID                    |
| saleNum        | Long     | 是       | 销量                      |
| skuPriceFee    | Double   | 是       | 规格售价                  |
| skuActualStock | Int      | 是       | 规格实际库存              |
| weight         | Double   | 是       | 商品重量                  |
| volume         | Double   | 是       | 商品体积                  |
| spuDetail      | Object   | 是       | 商品详情                  |

#### 5.2.商品详情

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-comm/spu/getSpu

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 否       | 商品ID   |

**返回参数：**

| 参数名称       | 参数类型 | 是否必须 | 参数说明                  |
| -------------- | -------- | -------- | ------------------------- |
| name           | String   | 是       | 商品名称                  |
| sellingPoint   | String   | 是       | 卖点                      |
| mainImgUrl     | String   | 是       | 商品介绍主图              |
| imgUrls        | String   | 是       | 商品图片 多个图片逗号分隔 |
| video          | String   | 是       | 商品视频                  |
| skuId          | Long     | 是       | 规格ID                    |
| saleNum        | Long     | 是       | 销量                      |
| skuPriceFee    | Double   | 是       | 规格售价                  |
| skuActualStock | Int      | 是       | 规格实际库存              |
| weight         | Double   | 是       | 商品重量                  |
| volume         | Double   | 是       | 商品体积                  |
| spuDetail      | Object   | 是       | 商品详情                  |

### 6.购物车

#### 6.1.购物车列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-comm/shopCartItem/getUserBasketList

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |
| search      | String   | 否       | 商品搜索       |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明       |
| ---------- | -------- | -------- | -------------- |
| pages      | Int      | 是       | 总页数         |
| total      | Int      | 是       | 总条数         |
| current    | Int      | 是       | 当前显示页     |
| size       | Int      | 是       | 每页显示条数   |
| records    | List     | 是       | 数据列表       |
|            |          |          | records        |
| id         | Long     | 是       | id             |
| shopId     | Long     | 是       | 店铺id         |
| spuId      | Long     | 是       | 商品ID         |
| skuId      | Long     | 是       | 规格ID         |
| userId     | Long     | 是       | 用户ID         |
| count      | Int      | 是       | 购物车产品数量 |
| shopName   | String   | 是       | 店铺名称       |
| spuName    | String   | 是       | 商品名称       |
| mainImgUrl | String   | 是       | 主图片         |
| priceFee   | Double   | 是       | 商品价格       |
| createTime | String   | 是       | 添加时间       |
| updateTime | String   | 是       | 更新时间       |

#### 6.2.添加购物车

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-comm/shopCartItem/addShopCartItem

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| skuId    | Long     | 是       | 规格ID   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 6.3.更新购物车

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-comm/shopCartItem/update

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明       |
| -------- | -------- | -------- | -------------- |
| id       | Long     | 是       | 购物车ID       |
| count    | Int      | 是       | 购物车产品数量 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 6.4.删除购物车

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-comm/shopCartItem/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | 购物车ID |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 6.5.清空购物车

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-comm/shopCartItem/clearShopCartItem

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          |          |          |          |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 7.通讯录

#### 7.1.用户好友列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userGoodFriend/getUserGoodFriendList

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                   |
| ---------- | -------- | -------- | -------------------------- |
| searchName | String   | 否       | 搜索条件（备注和昵称查找） |
| status     | String   | 是       | 状态(1、好友 2、黑名单)    |

**返回参数：**

| 参数名称     | 参数类型 | 是否必须 | 参数说明                |
| ------------ | -------- | -------- | ----------------------- |
| id           | Long     | 是       | id                      |
| userId       | Long     | 是       | 用户ID                  |
| goodFriendId | Long     | 是       | 好友ID                  |
| remarks      | Long     | 是       | 备注                    |
| remarksEn    | String   | 是       | 备注首字母              |
| status       | Int      | 是       | 状态(1、好友 2、黑名单) |
| nickname     | String   | 是       | 好友昵称                |
| headimgurl   | String   | 是       | 好友头像                |
| imAccount    | String   | 是       | im账号                  |
| yAccount     | String   | 是       | 域号                    |
| createTime   | String   | 是       | 添加时间                |
| updateTime   | String   | 是       | 更新时间                |

#### 7.2.查找好友

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/user/findUser

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明               |
| ---------- | -------- | -------- | ---------------------- |
| searchName | String   | 是       | 电话号码、环信ID、域号 |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                                                     |
| ---------- | -------- | -------- | ------------------------------------------------------------ |
| id         | Long     | 是       | 用户ID                                                       |
| phone      | Long     | 是       | 电话号码                                                     |
| nickname   | String   | 是       | 用户昵称                                                     |
| headimgurl | String   | 是       | 用户头像                                                     |
| sex        | Int      | 是       | 用户的性别，值为1时是男性<br />，值为2时是女性，<br />值为0时是未知 |
| imAccount  | String   | 是       | im账号                                                       |
| addr       | String   | 是       | 所在城市                                                     |
| souFlg     | Int      | 是       | 来源（1、电话号码 2、环信号 3、域号）                        |
| yAccount   | String   | 是       | 域号                                                         |

#### 7.3.发起添加好友申请

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userGoodFriendApply/addGoodFriendApply

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                                            |
| -------- | -------- | -------- | --------------------------------------------------- |
| userId   | Long     | 是       | 好友ID                                              |
| souFlg   | Int      | 是       | 来源（1、电话号码 2、环信号 3、域号 4、群 5、名片） |
| content  | String   | 否       | 内容                                                |
| remarks  | String   | 否       | 添加成功后好友备注                                  |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 7.4.新朋友列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userGoodFriendApply/getNewGoogFriendList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          |          |          |          |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                                                     |
| ---------- | -------- | -------- | ------------------------------------------------------------ |
| id         | Long     | 是       | 申请ID                                                       |
| userId     | Long     | 是       | 用户ID                                                       |
| content    | String   | 是       | 添加发送内容                                                 |
| phone      | Long     | 是       | 电话号码                                                     |
| nickname   | String   | 是       | 用户昵称                                                     |
| headimgurl | String   | 是       | 用户头像                                                     |
| sex        | Int      | 是       | 用户的性别，值为1时是男性<br />，值为2时是女性，<br />值为0时是未知 |
| imAccount  | String   | 是       | im账号                                                       |
| yAccount   | String   | 是       | 域号                                                         |
| status     | int      | 是       | 状态(1、申请中 2、通过 3、拒绝)                              |

#### 7.5.通过申请

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userGoodFriendApply/adoptApply

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | 申请ID   |
| remarks  | String   | 否       | 好友备注 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 7.6.拒绝申请

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userGoodFriendApply/refuseApply

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | 申请ID   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 7.7.根据ID 查询个人信息详情

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/user/findUserById

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | 好友ID   |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                                                     |
| ---------- | -------- | -------- | ------------------------------------------------------------ |
| id         | Long     | 是       | 用户ID                                                       |
| phone      | Long     | 是       | 电话号码                                                     |
| nickname   | String   | 是       | 用户昵称                                                     |
| headimgurl | String   | 是       | 用户头像                                                     |
| sex        | Int      | 是       | 用户的性别，值为1时是男性<br />，值为2时是女性，<br />值为0时是未知 |
| imAccount  | String   | 是       | im账号                                                       |
| addr       | String   | 是       | 所在城市                                                     |
| yAccount   | String   | 是       | 域号                                                         |
| souFlg     | Int      | 是       | 来源（1、电话号码 2、环信号 3、域号）                        |
| status     | Int      | 是       | 状态(1、好友 2、黑名单)                                      |
| remarks    | String   | 是       | 好友备注                                                     |

#### 7.8.设置备注

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userGoodFriend/setNotes

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| userId   | Long     | 是       | 好友ID   |
| remarks  | String   | 是       | 好友备注 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 7.9.加入或移除黑名单

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userGoodFriend/addOrRemoveBlacklists

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| userId   | Long     | 是       | 好友ID   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 7.10.删除好友

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userGoodFriend/removeUserGoodFriend

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| userId   | Long     | 是       | 好友ID   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 8.密码管理

#### 8.1.设置登录密码

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/dr-frame-auth/sysUser/setUpPassword

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| password | String   | 是       | 密码     |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 8.2.找回密码

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/dr-frame-auth/sysUser/appRetrievePassword

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| phone    | Long     | 是       | 电话号码 |
| password | String   | 是       | 密码     |
| verCode  | String   | 是       | 验证码   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 9.收货地址

#### 9.1.收货地址列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userAddress/getList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |

**返回参数：**

| 参数名称     | 参数类型 | 是否必须 | 参数说明         |
| ------------ | -------- | -------- | ---------------- |
| id           | Long     | 是       | 收货地址ID       |
| userId       | Long     | 是       | 用户ID           |
| receiver     | String   | 是       | 收货人           |
| provinceCode | Int      | 是       | 省ID             |
| province     | Int      | 是       | 省名称           |
| cityCode     | Int      | 是       | 城市ID           |
| city         | Int      | 是       | 城市名称         |
| areaCode     | Int      | 是       | 区ID             |
| area         | Int      | 是       | 区名称           |
| postCode     | Int      | 是       | 邮编             |
| addr         | String   | 是       | 详细地址         |
| mobile       | Long     | 是       | 联系电话         |
| commonAddr   | Int      | 是       | 是否默认地址 1是 |
| lng          | Double   | 是       | 经度             |
| lat          | Double   | 是       | 纬度             |
| addTime      | String   | 是       | 添加时间         |
| updateTime   | String   | 是       | 修改时间         |

#### 9.2.添加或编辑收货地址

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userAddress/saveOrUpdate

**请求参数：**

| 参数名称     | 参数类型 | 是否必须 | 参数说明         |
| ------------ | -------- | -------- | ---------------- |
| id           | Long     | 否       | 收货地址ID       |
| receiver     | String   | 是       | 收货人           |
| provinceCode | Int      | 是       | 省ID             |
| province     | Int      | 是       | 省名称           |
| cityCode     | Int      | 是       | 城市ID           |
| city         | Int      | 是       | 城市名称         |
| areaCode     | Int      | 是       | 区ID             |
| area         | Int      | 是       | 区名称           |
| postCode     | Int      | 否       | 邮编             |
| addr         | String   | 是       | 详细地址         |
| mobile       | Long     | 是       | 联系电话         |
| commonAddr   | Int      | 否       | 是否默认地址 1是 |
| lng          | Double   | 否       | 经度             |
| lat          | Double   | 否       | 纬度             |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 9.3.设置为默认地址

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userAddress/setDefaultAddress

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明   |
| -------- | -------- | -------- | ---------- |
| id       | Long     | 否       | 收货地址ID |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 9.4.删除收货地址

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userAddress/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明   |
| -------- | -------- | -------- | ---------- |
| id       | Long     | 否       | 收货地址ID |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 10.中国地市信息查询

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-cfg/cfgArea/getList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明   |
| -------- | -------- | -------- | ---------- |
| parentId | Int      | 否       | 地市父级ID |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                             |
| ---------- | -------- | -------- | ------------------------------------ |
| id         | Int      | 是       | 地市ID                               |
| parentId   | Int      | 是       | 地市父级ID                           |
| name       | String   | 是       | 地市名字（成都市）                   |
| mangerName | String   | 是       | 地市名字<br />（中国,四川省,成都市） |
| shortName  | String   | 是       | 地市名字（成都）                     |
| zipCode    | Int      | 是       | 邮政编码                             |
| lng        | Double   | 是       | 经度                                 |
| lat        | Double   | 是       | 纬度                                 |

### 11.协议

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-cfg/sysExplain/getSysExplain

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                                                     |
| -------- | -------- | -------- | ------------------------------------------------------------ |
| type     | Int      | 是       | 类型（1、隐私政策 2、服务协议 <br />3、账号注销须知 4、商品信息管理规范 <br />5、账号使用规范 6、支持的银行卡 <br />7、交易纠纷管理办法   8、禁售商品管理规范 <br />9、用户协议 10、商品说明） |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| title    | String   | 是       | 标题     |
| content  | String   | 是       | 说明内容 |

### 12.收藏

#### 12.1.收藏列表

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-app-user/userCollection/selectPage

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明     |
| ---------- | -------- | -------- | ------------ |
| pages      | Int      | 是       | 总页数       |
| total      | Int      | 是       | 总条数       |
| current    | Int      | 是       | 当前显示页   |
| size       | Int      | 是       | 每页显示条数 |
| records    | List     | 是       | 数据列表     |
|            |          |          | records      |
| id         | Long     | 是       | 收藏ID       |
| prodId     | Long     | 是       | 商品ID       |
| name       | String   | 是       | 商品名称     |
| mainImgUrl | String   | 是       | 商品图片     |
| priceFee   | Double   | 是       | 销售价格     |
| addTime    | String   | 是       | 添加时间     |
| updateTime | String   | 是       | 更新时间     |

#### 12.2.收藏商品

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-app-user/userCollection/collection

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| prodId   | Long     | 是       | 商品ID   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 12.3.取消收藏

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-app-user/userCollection/cancelCollection

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| prodId   | Long     | 是       | 商品ID   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 13.支付

#### 13.1.钱包

##### 13.1.1.创建钱包

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-pay/wallat/walletCreate

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                                                     |
| ---------- | -------- | -------- | ------------------------------------------------------------ |
| name       | String   | 是       | 姓名                                                         |
| idCardNo   | String   | 是       | 证件号码                                                     |
| mobile     | String   | 是       | 注册手机号 码                                                |
| profession | String   | 是       | 职业<br />固定值为以下 <br />A:各类专业，技术人员 <br />B:国家机关，党群组织，企事业单 位的负责人 <br />C:办事人员和有关人员 <br />D:商业工作人员 <br />E:服务性工作人员 <br />F:农林牧渔劳动者 <br />G:生产工作，运输工作和部分体力劳动者 |
| mac        | String   | 是       | MAC 地址<br />客户端的 MAC 地址,字母之间用“:” 连接<br/>如果 IOS 不能获取，请传默认值: 00:00:00:00:00:00 |
| nickName   | String   | 否       | 用户昵称                                                     |

**返回参数：**

| 参数名称         | 参数中文名称 | 参数说明                                                     |
| ---------------- | ------------ | ------------------------------------------------------------ |
| status           | 响应状态     | 响应正常 SUCCESS 响应异常 FAIL                               |
| walletStatus     | 钱包状态     | 激活:ACTIVATE 失败:FAIL                                      |
| operatorRzStatus | 运营商认证   | 成功:SUCCESS 失败:FAIL                                       |
| merchantId       | 商户编号     | 同请求参数                                                   |
| requestId        | 订单号       | 同请求参数                                                   |
| merchantUserId   | 商户用户 ID  | 同请求参数                                                   |
| walletId         | 钱包 ID      | 用户钱包 ID 在我司的唯一编号                                 |
| idCardRzStatus   | 实名认证     | 成功:SUCCESS 失败:FAIL                                       |
| riskScore        | 注册风险评分 | 返回是 0~100 正整数                                          |
| secretKey        | 证书授权码   | 用户开户后首次唤起<br /> SDK 自动安装数字证书时使用，<br />10 分 钟内有效  可以在唤起<br /> SDK 中完成  1、安装数字证书 |

##### 13.1.2.账户查询

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/wallat/walletQuery

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| walletId | String   | 是       | 钱包ID   |

**返回参数：**

| 参数名称         | 参数中文名称      | 参数说明                                                     |
| ---------------- | ----------------- | ------------------------------------------------------------ |
| status           | 响应状态          | 响应正常 SUCCESS 响应异常 FAIL                               |
| idCardRzStatus   | 实名认证          | 成功:SUCCESS 失败:FAIL                                       |
| operatorRzStatus | 运营商认证        | 成功:SUCCESS 失败:FAIL                                       |
| personRzStatus   | 人像认证          | 没有校验过:INIT 成功:SUCCESS 失败:FAIL                       |
| merchantId       | 商户编号          | 同请求参数                                                   |
| requestId        | 订单号            | 同请求参数                                                   |
| merchantUserId   | 商户用户 ID       | 同请求参数                                                   |
| walletId         | 钱包 ID           | 用户钱包 ID 在我司的唯一编号                                 |
| setUpPasswrod    | 是否设置支付密 码 | 是:true 否:false                                             |
| idCardType       | 证件类型          | 默认:IDCARD 身份证                                           |
| idCardNoDesc     | 身份证号码        | 身份证掩码                                                   |
| mobileDesc       | 注册手机          | 手机掩码                                                     |
| nameDesc         | 姓名              | 姓名掩码                                                     |
| profession       | 职业              | 同请求参数                                                   |
| nickName         | 用户昵称          |                                                              |
| riskScore        | 注册风险评分      | 返回是 0~100 正整数                                          |
| accountType      | 账户类型          | 钱包账户类别(共有 3 类)  I 类账户:自账户开立起，<br />使用余额支付累计不可超过 1000 元(<br />包括支付账户向客户本人同名银行账户转账)认证次数 1-2 次账户类型 II 类账户:<br />使用余额支付年累计不可超过 10 万元 <br />(不包 括支付账户向客户本人同名银行<br />账户转账)认证次数 3-4 次 III 类账户:使<br />用余额支付年累计不可超过 20 万元 (不 <br />包括支付账户向客户本人同名银行账户<br />转账)认证次数 5 次获取 hmac 的方法见表 10，<br />参数顺序按照键名首字母从<br /> a-z 拼接对应的键值中间用#号隔开。 |
|                  |                   |                                                              |
| authTimes        | 认证次数          | 实名认证，运营商认证，人脸识别，银行卡鉴权(非同一银 行)，累加计数 |
| balance          | 钱包余额          | 单位为 分                                                    |
| createDateTime   | 创建时间          | 格式:yyyy-MM-dd HH:mm:ss                                     |
| walletStatus     | 钱包状态          | 初始化:INIT <br />激活:ACTIVATE<br />冻结:FREEZED <br />失败:FAIL <br />销户:DESTROY <br />止付:NOPAYMENT |

##### 13.1.3.账户修改

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/wallat/walletUpdateWalletInfo

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| mobile   | String   | 是       | 手机号码 |
| nickName | String   | 是       | 用户昵称 |

**返回参数：**

| 参数名称         | 参数中文名称 | 参数说明                               |
| ---------------- | ------------ | -------------------------------------- |
| status           | 响应状态     | 响应正常 SUCCESS 响应异常 FAIL         |
| modifyStatus     | 修改状态     | 成功 SUCCESS 失败 FAIL                 |
| operatorRzStatus | 运营商认证   | 成功:SUCCESS 失败:FAIL                 |
| personRzStatus   | 人像认证     | 没有校验过:INIT 成功:SUCCESS 失败:FAIL |
| merchantId       | 商户编号     | 同请求参数                             |
| requestId        | 订单号       | 同请求参数                             |
| walletId         | 钱包 ID      | 用户钱包 ID 在我司的唯一编号           |

##### 13.1.4.账户变更通知

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/wallat/callback

#### 13.2.充值

##### 13.2.1.充值预下单

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/recharge/rechargeOrder

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                                                  |
| -------- | -------- | -------- | --------------------------------------------------------- |
| amount   | String   | 是       | 充值金额（以分为单位）                                    |
| remark   | String   | 否       | 备注（商户在首信易为订单进行备注，通过 支付结果返回商户） |

**返回参数：**

| 参数名称        | 参数中文名称 | 参数说明                               |
| --------------- | ------------ | -------------------------------------- |
| status          | 响应状态     | 响应正常 SUCCESS 响应异常 FAIL         |
| orderStatus     | 充值状态     | 初始化状态:INIT                        |
| merchantId      | 商户编号     | 同请求参数                             |
| requestId       | 订单号       | 同请求参数                             |
| serialNumber    | 交易流水号   | 首信易支付系统交易流水号               |
| walletId        | 钱包 ID      | 用户钱包 ID 在我司的唯一编号           |
| currency        | 币种         | 默认:CNY                               |
| amount          | 金额         | 同请求参数。                           |
| token           | 票据         | 限制调用移动端权限的。(仅一次)         |
| remark          | 备注         | 在下单请求中提交的备注信息，返回给商户 |
| createDateTi me | 创建时间     | 预下单时间 格式:yyyy-MM-dd HH:mm:ss    |

##### 13.2.2.订单查询

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/recharge/rechargeQuery

**请求参数：**

| 参数名称  | 参数类型 | 是否必须 | 参数说明 |
| --------- | -------- | -------- | -------- |
| requestId | String   | 是       | 订单号   |

**返回参数：**见第二份文档

#### 13.3.转账

##### 13.3.1.转账预下单

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/transfer/transferCreateOrder

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明             |
| -------- | -------- | -------- | -------------------- |
| amount   | String   | 是       | 转账金额(以分为单位) |
| currency | String   | 是       | 币种(CNY 人民币)     |

**返回参数：**见第二份文档

##### 13.3.2.转账确认

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/transfer/transferConfirmOrder

**请求参数：**

| 参数名称     | 参数类型 | 是否必须 | 参数说明                       |
| ------------ | -------- | -------- | ------------------------------ |
| serialNumber | String   | 是       | 流水号：转账预下单返回的流水号 |

**返回参数：**见第二份文档

##### 13.3.3.转账拒收

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/transfer/transferRefuseOrder

**请求参数：**

| 参数名称     | 参数类型 | 是否必须 | 参数说明                       |
| ------------ | -------- | -------- | ------------------------------ |
| serialNumber | String   | 是       | 流水号：转账预下单返回的流水号 |

**返回参数：**见第二份文档

##### 13.3.4.转账查询

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/transfer/transferRefuseOrder

**请求参数：**

| 参数名称  | 参数类型 | 是否必须 | 参数说明 |
| --------- | -------- | -------- | -------- |
| requestId | String   | 是       | 订单号   |

**返回参数：**见第二份文档

##### 13.3.5.转账超时退还

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/transfer/transferTimeoutReturn

**请求参数：**

| 参数名称  | 参数类型 | 是否必须 | 参数说明 |
| --------- | -------- | -------- | -------- |
| requestId | String   | 是       | 订单号   |

**返回参数：**见第二份文档

#### 13.4.提现

##### 13.4.1.提现预下单

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/withholding

**请求参数：**

| 参数名称      | 参数类型 | 是否必须 | 参数说明                 |
| ------------- | -------- | -------- | ------------------------ |
| amount        | String   | 是       | 提现金额(以分为单位)     |
| arrivalAmount | String   | 是       | 实际到账金额(以分为单位) |
| currency      | String   | 是       | 币种(CNY 人民币)         |

**返回参数：**见第二份文档

##### 13.4.2.提现查询

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/withholding/withholdingQuery

**请求参数：**

| 参数名称  | 参数类型 | 是否必须 | 参数说明 |
| --------- | -------- | -------- | -------- |
| requestId | String   | 是       | 订单号   |

**返回参数：**见第二份文档

#### 13.4.获取token

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-pay/clientToken/getClientToken

**请求参数：**

| 参数名称     | 参数类型 | 是否必须 | 参数说明                                                     |
| ------------ | -------- | -------- | ------------------------------------------------------------ |
| businessType | String   | 是       | 业务类型（唤起安全设置页面:ACCESS_SAFETY <br />唤起卡列表页面:ACCESS_CARDlIST） |

**返回参数：**见第二份文档

#### 13.5.交易记录

##### 13.5.1.交易记录列表

**请求说明：**HTTP POST

**请求地址:** http://66.42.60.149/zuul/reception-api-pay/information/tradeRecordBill

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                                                     |
| ---------- | -------- | -------- | ------------------------------------------------------------ |
| requestId  | String   | 否       | 订单号                                                       |
| pageIndex  | String   | 是       | 当前页数                                                     |
| pageSize   | String   | 否       | 每页的条数（如果为空 <br />默认 20 条,最大 100 条）          |
| direction  | String   | 否       | 资金方向：增加(入账):INCREASE <br />减少(出账):DECREASE <br />如果不选，默认包括所有资金方向。 |
| tradeType  | String   | 否       | 充值:WEBOX_RECHARGE <br />转账:WEBOX_TRANSFER <br />转账退款: WEBOX_TRANSFER_REFUND<br /> 提现:WEBOX_WITHHOLDING <br />红包:WEBOX_REDPACKET <br />一对一红包: WEBOX_REDPACKET_ONE_TO_O NE<br />普通群红包:WEBOX_REDPACKET_GROUP_N ORMAL<br/>拼手气红包: WEBOX_REDPACKET_GROUP_LU CK<br />红包退款:WEBOX_REDPACKET_REFUND<br/>企业付款:WEBOX_MERCHANT_RECHARGE <br />支付:WEBOX_APP_PAY <br />支付退款: WEBOX_APP_PAY_REFUND <br />分账:SPLIT_PAYMENT <br />分账退款: SPLIT_REFUND_PAYMENT <br />如果不选，默认包括所有交易类型。 |
| queryMonth | String   | 是       | 查询月份（格式:yyyy-MM 例如:2020-05）                        |

**返回参数：**见第二份文档

##### 13.5.2.删除交易记录

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-pay/information/tradeRecordDelete

**请求参数：**

| 参数名称       | 参数类型 | 是否必须 | 参数说明   |
| -------------- | -------- | -------- | ---------- |
| tradeRecordIds | String   | 是       | 交易记录ID |

**返回参数：**见第二份文档

### 14.环信

#### 14.1.接口调用前缀地址获取

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-app-user/hx/getUrl

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                                                     |
| -------- | -------- | -------- | ------------------------------------------------------------ |
| url      | String   | 是       | 环信请求地址（<br />url:http://www.hx.com/{org_name}/{app_name}） |

#### 14.2.access_token获取

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-app-user/hx/getAccessToken

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |

**返回参数：**

| 参数名称     | 参数类型 | 是否必须 | 参数说明  |
| ------------ | -------- | -------- | --------- |
| access_token | String   | 是       | 环信token |

#### 14.3.获取用户加入群列表

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-app-user/groups/getUserGroupList

**请求参数：**

| 参数名称  | 参数类型 | 是否必须 | 参数说明   |
| --------- | -------- | -------- | ---------- |
| imAccount | String   | 是       | 用户IM账号 |

**返回参数：**

| 参数名称          | 参数类型 | 是否必须 | 参数说明                                                     |
| ----------------- | -------- | -------- | ------------------------------------------------------------ |
| id                | String   | 是       | 群组 ID                                                      |
| name              | String   | 是       | 群组名称                                                     |
| description       | String   | 是       | 群组描述                                                     |
| hxPublic          | Int      | 是       | 群组类型：true：公开群，false：私有群。                      |
| membersonly       | Int      | 是       | 加入群组是否需要群主或者群管理员审批。true：是，false：否。  |
| allowinvites      | Int      | 是       | 是否允许群成员邀请别人加入此群。 <br />true：允许群成员邀请人加入此群，<br />false：只有群主才可以往群里加人 |
| maxusers          | Long     | 是       | 群成员上限                                                   |
| affiliationsCount | Long     | 是       | 现有成员总数                                                 |
| owner             | String   | 是       | 群主的环信 ID                                                |
| inviteNeedConfirm | Int      | 是       | 邀请加群，被邀请人是否需要确认                               |
| mute              | Int      | 是       | 是否全员禁言。true：是，false：否。                          |
| headimgurl        | String   | 是       | 群主头像                                                     |
| userGroupName     | String   | 是       | 用户在群里昵称                                               |
| isTop             | Int      | 是       | 是否置顶（1置顶 0不置顶）                                    |

#### 14.4.修改群信息

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-app-user/groups/modifyGroup

**请求参数：**

| 参数名称     | 参数类型 | 是否必须 | 参数说明                                                     |
| ------------ | -------- | -------- | ------------------------------------------------------------ |
| groupId      | String   | 是       | 群组ID                                                       |
| username     | String   | 是       | 环信用户ID                                                   |
| groupname    | String   | 否       | 群组名称，修改时值不能包<br />含斜杠（“/“），最大长度为128字符。 |
| description  | String   | 否       | 群组描述，修改时值不能包<br />含斜杠（”/“），最大长度为512字符。 |
| maxusers     | String   | 否       | 群组成员最大数（包括群主），值为数值类型。                   |
| membersonly  | String   | 否       | 加入群组是否需要群主或者群管理员审批。true：是，false：否。  |
| allowinvites | String   | 否       | 是否允许群成员邀请别人加入此群。 true：<br />允许群成员邀请人加入此群，false：只有群主才可以往群里加人。 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 14.5.群成员列表

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-app-user/groups/getGroupUserList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| groupId  | String   | 是       | 群组ID   |

**返回参数：**

| 参数名称      | 参数类型 | 是否必须 | 参数说明       |
| ------------- | -------- | -------- | -------------- |
| id            | Long     | 是       | id             |
| phone         | Long     | 是       | 电话号码       |
| nickname      | String   | 是       | 昵称           |
| headimgurl    | String   | 是       | 用户头像       |
| imAccount     | String   | 是       | im账号         |
| yAccount      | String   | 是       | 域号           |
| userGroupName | String   | 是       | 用户在群里昵称 |

#### 14.6.设置在群组备注、和群是否置顶

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-app-user/userGroups/saveOrUpdate

**请求参数：**

| 参数名称      | 参数类型 | 是否必须 | 参数说明     |
| ------------- | -------- | -------- | ------------ |
| groupId       | String   | 是       | 群组ID       |
| imAccount     | String   | 是       | 用户IM账号   |
| userGroupName | String   | 否       | 群里昵称     |
| isTop         | Int      | 否       | 群组是否置顶 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 14.7.查询群组详情

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-app-user/groups/getUserGroup

**请求参数：**

| 参数名称  | 参数类型 | 是否必须 | 参数说明   |
| --------- | -------- | -------- | ---------- |
| groupId   | String   | 是       | 群组ID     |
| imAccount | String   | 是       | 用户IM账号 |

**返回参数：**

| 参数名称          | 参数类型 | 是否必须 | 参数说明                                                     |
| ----------------- | -------- | -------- | ------------------------------------------------------------ |
| id                | String   | 是       | 群组 ID                                                      |
| name              | String   | 是       | 群组名称                                                     |
| description       | String   | 是       | 群组描述                                                     |
| hxPublic          | Int      | 是       | 群组类型：true：公开群，false：私有群。                      |
| membersonly       | Int      | 是       | 加入群组是否需要群主或者群管理员审批。true：是，false：否。  |
| allowinvites      | Int      | 是       | 是否允许群成员邀请别人加入此群。 <br />true：允许群成员邀请人加入此群，<br />false：只有群主才可以往群里加人 |
| maxusers          | Long     | 是       | 群成员上限                                                   |
| affiliationsCount | Long     | 是       | 现有成员总数                                                 |
| owner             | String   | 是       | 群主的环信 ID                                                |
| inviteNeedConfirm | Int      | 是       | 邀请加群，被邀请人是否需要确认                               |
| mute              | Int      | 是       | 是否全员禁言。true：是，false：否。                          |
| headimgurl        | String   | 是       | 群主头像                                                     |
| userGroupName     | String   | 是       | 用户在群里昵称                                               |
| isTop             | Int      | 是       | 是否置顶（1置顶 0不置顶）                                    |

#### 14.8.转让群

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-app-user/groups/transferGroup

**请求参数：**

| 参数名称  | 参数类型 | 是否必须 | 参数说明     |
| --------- | -------- | -------- | ------------ |
| groupId   | String   | 是       | 群组ID       |
| imAccount | String   | 是       | 新群主IM账号 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 14.9.群管理员列表

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-app-user/groups/getGroupAdminUserList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| groupId  | String   | 是       | 群组ID   |

**返回参数：**

| 参数名称      | 参数类型 | 是否必须 | 参数说明       |
| ------------- | -------- | -------- | -------------- |
| id            | Long     | 是       | id             |
| phone         | Long     | 是       | 电话号码       |
| nickname      | String   | 是       | 昵称           |
| headimgurl    | String   | 是       | 用户头像       |
| imAccount     | String   | 是       | im账号         |
| yAccount      | String   | 是       | 域号           |
| userGroupName | String   | 是       | 用户在群里昵称 |

#### 14.10.添加群成员（这是系统级添加不受群限制条件）

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-app-user/groups/addGroupUser

**请求参数：**

| 参数名称  | 参数类型 | 是否必须 | 参数说明     |
| --------- | -------- | -------- | ------------ |
| groupId   | String   | 是       | 群组ID       |
| imAccount | String   | 是       | 新成员IM账号 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 14.11.批量添加群成员（这是系统级添加不受群限制条件）

**请求说明：**HTTP POST

**请求地址：：http://66.42.60.149/zuul/reception-api-app-user/groups/addGroupUsers

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                       |
| ---------- | -------- | -------- | ------------------------------ |
| groupId    | String   | 是       | 群组ID                         |
| imAccounts | String   | 是       | 新成员IM账号（以逗号进行分隔） |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 15.图片上传

#### 15.1.单张上传

**请求说明：**HTTP POST 表单提交

**请求地址：http://66.42.60.149/zuul/reception-api-cfg/picture/upload

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| file     | file     | 是       | 文件     |

**返回参数：**

| 参数名称  | 参数类型 | 是否必须 | 参数说明 |
| --------- | -------- | -------- | -------- |
| imageName | String   | 是       | 图片名称 |
| url       | String   | 是       | 图片地址 |

#### 15.2.多张上传

**请求说明：**HTTP POST 表单提交

**请求地址：http://66.42.60.149/zuul/reception-api-cfg/picture/uploads

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| file     | file     | 是       | 文件     |

**返回参数：**

| 参数名称  | 参数类型 | 是否必须 | 参数说明 |
| --------- | -------- | -------- | -------- |
|           | List     |          | 图片列表 |
| imageName | String   | 是       | 图片名称 |
| url       | String   | 是       | 图片地址 |

### 16.订单

#### 16.1.下单

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-app-user/order/placeOrder

**请求参数：**

| 参数名称      | 参数类型 | 是否必须 | 参数说明       |
| ------------- | -------- | -------- | -------------- |
| basketList    | List     | 是       | 购物车ID列表   |
| userAddressId | Long     | 是       | 用户收货地址ID |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 16.2.立即下单

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-app-user/order/spuPlaceOrder

**请求参数：**

| 参数名称      | 参数类型 | 是否必须 | 参数说明       |
| ------------- | -------- | -------- | -------------- |
| skuId         | Long     | 是       | 规格ID         |
| count         | Long     | 是       | 规格数量       |
| userAddressId | Long     | 是       | 用户收货地址ID |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 16.3.订单列表

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-app-user/order/selectPage

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明                                         |
| ----------- | -------- | -------- | ------------------------------------------------ |
| currentPage | Int      | 是       | 显示第几页                                       |
| pageSize    | Int      | 是       | 每页显示多少条                                   |
| type        | Int      | 是       | 订单状态 ：1全部 2待付款 3待发货 4待收货 5已完成 |

**返回参数：**

| 参数名称     | 参数类型 | 是否必须 | 参数说明                                                     |
| ------------ | -------- | -------- | ------------------------------------------------------------ |
| pages        | Int      | 是       | 总页数                                                       |
| total        | Int      | 是       | 总条数                                                       |
| current      | Int      | 是       | 当前显示页                                                   |
| size         | Int      | 是       | 每页显示条数                                                 |
| records      | List     | 是       | 数据列表                                                     |
|              |          |          | records                                                      |
| id           | Long     | 是       | 订单ID                                                       |
| shopId       | Long     | 是       | 店铺id                                                       |
| userId       | Long     | 是       | 用户ID                                                       |
| deliveryType | Int      | 是       | 配送类型：无需快递                                           |
| shopName     | String   | 是       | 店铺名称                                                     |
| total        | Double   | 是       | 订单总额                                                     |
| type         | Int      | 是       | 订单状态 ：1全部 2待付款 3待发货 4待收货 5已完成             |
| status       | Int      | 是       | 订单状态 1:待付款 2:待发货 <br />3:待收货(已发货) 5:成功 6:失败 |
| allCount     | Int      | 是       | 订单商品总数                                                 |
| payTime      | String   | 是       | 付款时间                                                     |
| deliveryTime | String   | 是       | 发货时间                                                     |
| finallyTime  | String   | 是       | 完成时间                                                     |
| settledTime  | String   | 是       | 结算时间                                                     |
| cancelTime   | String   | 是       | 取消时间                                                     |
| isPayed      | Int      | 是       | 是否已支付，1.已支付0.未支付                                 |
| closeType    | Int      | 是       | 订单关闭原因 1-超时未支付<br /> 4-买家取消 5-已通过货到付款交易 |
| create_time  | String   | 是       | 下单时间                                                     |
| spuName      | String   | 是       | 商品名称                                                     |
| spuImage     | String   | 是       | 商品图片                                                     |

#### 16.4.取消订单

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-app-user/order/cancelOrder

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | 订单ID   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 17.个人中心

#### 17.1.查询个人信息详情

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/user/getUserById

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                                                     |
| ---------- | -------- | -------- | ------------------------------------------------------------ |
| phone      | Long     | 是       | 电话号码                                                     |
| nickname   | String   | 是       | 用户昵称                                                     |
| headimgurl | String   | 是       | 用户头像                                                     |
| sex        | Int      | 是       | 用户的性别，值为1时是男性<br />，值为2时是女性，<br />值为0时是未知 |
| imAccount  | String   | 是       | im账号                                                       |
| addr       | String   | 是       | 所在城市                                                     |
| yAccount   | String   | 是       | 域号                                                         |

#### 17.2.修改个人信息

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/user/modifyUser

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                                                     |
| ---------- | -------- | -------- | ------------------------------------------------------------ |
| nickname   | String   | 是       | 用户昵称                                                     |
| headimgurl | String   | 是       | 用户头像                                                     |
| sex        | Int      | 是       | 用户的性别，值为1时是男性<br />，值为2时是女性，<br />值为0时是未知 |
| addr       | String   | 是       | 所在城市                                                     |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 17.3.个人隐私查询

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userPrivacy/getUserPrivacy

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |

**返回参数：**

| 参数名称         | 参数类型 | 是否必须 | 参数说明                                  |
| ---------------- | -------- | -------- | ----------------------------------------- |
| isPhone          | Int      | 否       | 是否可以通过手机号查找（0、否 1、是）     |
| isGroup          | Int      | 否       | 是否可以通过群添加好友（0、否 1、是）     |
| isQr             | Int      | 否       | 是否可以通过二维码添加好友（0、否 1、是） |
| isImAccount      | Int      | 否       | 是否可以通过域聊号添加好友（0、否 1、是） |
| enableValidation | Int      | 否       | 是否开启安全验证（0、否 1、是）           |

#### 17.4.个人隐私设置

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userPrivacy/saveOrUpdate

**请求参数：**

| 参数名称         | 参数类型 | 是否必须 | 参数说明                                  |
| ---------------- | -------- | -------- | ----------------------------------------- |
| isPhone          | Int      | 否       | 是否可以通过手机号查找（0、否 1、是）     |
| isGroup          | Int      | 否       | 是否可以通过群添加好友（0、否 1、是）     |
| isQr             | Int      | 否       | 是否可以通过二维码添加好友（0、否 1、是） |
| isImAccount      | Int      | 否       | 是否可以通过域聊号添加好友（0、否 1、是） |
| enableValidation | Int      | 否       | 是否开启安全验证（0、否 1、是）           |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 18.客服电话

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-cfg/sysDic/getCustomerServiceTelephone

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| val      | String   | 是       | 客服电话 |

### 19.检查APP是否最新版

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-cfg/appVersion/getNewAppVersion

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明 |
| ----------- | -------- | -------- | -------- |
| versionCode | Int      | 是       | 版本号   |

**返回参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明     |
| ----------- | -------- | -------- | ------------ |
| versionCode | Int      | 是       | 版本号       |
| androidUrl  | String   | 是       | 安卓下载地址 |
| context     | String   | 是       | 更新内容     |

### 20.系统消息列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userRecordLog/getSysMsgList

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |

| 参数名称       | 参数类型 | 是否必须 | 参数说明                                                     |
| -------------- | -------- | -------- | ------------------------------------------------------------ |
| pages          | Int      | 是       | 总页数                                                       |
| total          | Int      | 是       | 总条数                                                       |
| current        | Int      | 是       | 当前显示页                                                   |
| size           | Int      | 是       | 每页显示条数                                                 |
| records        | List     | 是       | 数据列表                                                     |
|                |          |          | records                                                      |
| id             | Long     | 是       | 消息ID                                                       |
| type           | Int      | 是       | 消息类型（1、转账 2、充值提现 3、商户消费 4、会员 5、系统消息） |
| payType        | Int      | 是       | 收入类型（1、支出 2、收入）                                  |
| title          | String   | 是       | 标题                                                         |
| msgContent     | String   | 是       | 消息内容                                                     |
| link           | String   | 是       | 链接                                                         |
| title          | String   | 是       | 标题（eg:转账-转给张三）                                     |
| transactionNo  | String   | 是       | 交易订单号                                                   |
| merchantNo     | String   | 是       | 商户订单号                                                   |
| amountMoney    | Double   | 是       | 金额                                                         |
| status         | Int      | 是       | 状态(1、申请提现、 2、交易成功 3、交易失败)                  |
| addTime        | String   | 是       | 时间（下单时间、发布时间）                                   |
| collectionTime | String   | 是       | 收款时间                                                     |

### 21.会员

#### 21.1.会员价格列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-cfg/sysVip/getSysVipList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |

| 参数名称 | 参数类型 | 是否必须 | 参数说明             |
| -------- | -------- | -------- | -------------------- |
| id       | Long     | 是       | 会员ID               |
| vipPrice | Double   | 是       | 标题                 |
| mothNum  | Int      | 是       | 开通时长（单位月份） |

#### 21.2.会员下单

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-cfg/sysVip/placeOrder

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | 会员ID   |

| 参数名称  | 参数类型 | 是否必须 | 参数说明 |
| --------- | -------- | -------- | -------- |
| orderCode | String   | 是       | 订单号   |

#### 21.3.会员图片

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-cfg/sysDic/getSysVipImg

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明     |
| -------- | -------- | -------- | ------------ |
| val      | String   | 是       | 会员图片连接 |

### 22.账单

#### 22.1.账单列表

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-app-user/userRecordLog/getUserRecordLogList

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明          |
| ----------- | -------- | -------- | ----------------- |
| currentPage | Int      | 是       | 显示第几页        |
| pageSize    | Int      | 是       | 每页显示多少条    |
| month       | Int      | 否       | 月份（eg:202111） |

**返回参数：**

| 参数名称       | 参数类型 | 是否必须 | 参数说明                                    |
| -------------- | -------- | -------- | ------------------------------------------- |
| pages          | Int      | 是       | 总页数                                      |
| total          | Int      | 是       | 总条数                                      |
| current        | Int      | 是       | 当前显示页                                  |
| size           | Int      | 是       | 每页显示条数                                |
| records        | List     | 是       | 数据列表                                    |
|                |          |          | records                                     |
| payType        | Int      | 是       | 收入类型（1、支出 2、收入）                 |
| title          | String   | 是       | 标题（eg:转账-转给张三）                    |
| transactionNo  | String   | 是       | 交易订单号                                  |
| merchantNo     | String   | 是       | 商户订单号                                  |
| amountMoney    | Double   | 是       | 金额                                        |
| status         | Int      | 是       | 状态(1、申请提现、 2、交易成功 3、交易失败) |
| addTime        | String   | 是       | 下单时间                                    |
| collectionTime | String   | 是       | 收款时间                                    |

### 23.公告

#### 23.1.公告列表

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-cfg/sysMsg/getMsgPageList

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |

**返回参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明     |
| ----------- | -------- | -------- | ------------ |
| pages       | Int      | 是       | 总页数       |
| total       | Int      | 是       | 总条数       |
| current     | Int      | 是       | 当前显示页   |
| size        | Int      | 是       | 每页显示条数 |
| records     | List     | 是       | 数据列表     |
|             |          |          | records      |
| id          | Long     | 是       | 消息ID       |
| title       | String   | 是       | 标题         |
| msgContent  | String   | 是       | 消息内容     |
| link        | String   | 是       | 链接         |
| create_time | String   | 是       | 消息发布时间 |

### 24.投诉

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-cfg/message/saveOrUpdate

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| contact  | String   | 否       | 联系方式 |
| content  | String   | 是       | 投诉内容 |
| imgUrl   | String   | 否       | 图片     |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 状态码说明

| 状态码 | 说明                   |
| ------ | ---------------------- |
| 401    | 身份验证失败 token过期 |
| 500    | 系统错误               |
| 200    | 成功                   |


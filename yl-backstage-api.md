## 1.平台

### 1.属性

#### 1.1.属性列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attr/getAttrPagerList

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明               |
| ---------- | -------- | -------- | ---------------------- |
| pages      | Int      | 是       | 总页数                 |
| total      | Int      | 是       | 总条数                 |
| current    | Int      | 是       | 当前显示页             |
| size       | Int      | 是       | 每页显示条数           |
| records    | List     | 是       | 数据列表               |
|            |          |          | records                |
| id         | Long     | 是       | attr id                |
| name       | String   | 是       | 属性名称               |
| desc       | String   | 是       | 属性描述               |
| searchType | Int      | 是       | 0:不需要，1:需要       |
| attrType   | Int      | 是       | 0:销售属性，1:基本属性 |
| valueStr   | String   | 是       | 属性值（以/分隔）      |
| createTime | String   | 是       | 添加时间               |
| updateTime | String   | 是       | 更新时间               |

#### 1.2.属性列表查询

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attr/getAttrList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| shopId   | Long     | 是       | 店铺ID   |
| spuId    | Long     | 否       | 商品ID   |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明               |
| ---------- | -------- | -------- | ---------------------- |
| id         | Long     | 是       | attr id                |
| shopId     | Long     | 是       | 店铺Id                 |
| name       | String   | 是       | 属性名称               |
| desc       | String   | 是       | 属性描述               |
| searchType | Int      | 是       | 0:不需要，1:需要       |
| attrType   | Int      | 是       | 0:销售属性，1:基本属性 |
| valueStr   | String   | 是       | 属性值（以/分隔）      |
| createTime | String   | 是       | 添加时间               |
| updateTime | String   | 是       | 更新时间               |
| isTick     | Boolean  | 是       | 是否选中               |

#### 1.3.添加或编辑属性

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attr/saveOrUpdate

**请求参数：**

| 参数名称      | 参数类型 | 是否必须 | 参数说明         |
| ------------- | -------- | -------- | ---------------- |
| id            | Long     | 否       | attr id          |
| name          | String   | 否       | 属性名称         |
| desc          | String   | 否       | 属性描述         |
| attrValueList |          |          |                  |
| value         |          |          |                  |
| searchType    | Int      | 否       | 0:不需要，1:需要 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 1.4.删除属性

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attr/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | attr id  |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 1.5.属性值列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attrValue/getList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| attrId   | Long     | 是       | 属性id   |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明 |
| ---------- | -------- | -------- | -------- |
| id         | Long     | 是       | 属性值id |
| attrId     | Long     | 是       | 属性id   |
| value      | String   | 是       | 属性值   |
| createTime | String   | 是       | 添加时间 |
| updateTime | String   | 是       | 更新时间 |

#### 1.6.添加或修改属性值

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attrValue/saveOrUpdate

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 否       | 属性值id |
| attrId   | Long     | 否       | 属性id   |
| value    | String   | 否       | 属性值   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 1.7.删除属性值

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attrValue/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | 属性值id |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 2.品牌

#### 2.1.品牌列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/brand/selectPage

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |
| name        | String   | 否       | 品牌名称       |

**返回参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明                             |
| ----------- | -------- | -------- | ------------------------------------ |
| pages       | Int      | 是       | 总页数                               |
| total       | Int      | 是       | 总条数                               |
| current     | Int      | 是       | 当前显示页                           |
| size        | Int      | 是       | 每页显示条数                         |
| records     | List     | 是       | 数据列表                             |
|             |          |          | records                              |
| id          | Long     | 是       | attr id                              |
| name        | String   | 是       | 品牌名称                             |
| descr       | String   | 是       | 品牌描述                             |
| imgUrl      | String   | 是       | 品牌logo图片                         |
| firstLetter | String   | 是       | 检索首字母                           |
| seq         | Int      | 是       | 排序                                 |
| status      | Int      | 是       | 状态 1:enable, 0:disable, -1:deleted |
| createTime  | String   | 是       | 添加时间                             |
| updateTime  | String   | 是       | 更新时间                             |

#### 2.2.品牌列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/brand/getList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| name     | String   | 否       | 品牌名称 |

**返回参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明                             |
| ----------- | -------- | -------- | ------------------------------------ |
| id          | Long     | 是       | 品牌id                               |
| name        | String   | 是       | 品牌名称                             |
| descr       | String   | 是       | 品牌描述                             |
| imgUrl      | String   | 是       | 品牌logo图片                         |
| firstLetter | String   | 是       | 检索首字母                           |
| seq         | Int      | 是       | 排序                                 |
| status      | Int      | 是       | 状态 1:enable, 0:disable, -1:deleted |
| createTime  | String   | 是       | 添加时间                             |
| updateTime  | String   | 是       | 更新时间                             |

#### 2.3.添加或编辑品牌

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/brand/saveOrUpdate

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                             |
| -------- | -------- | -------- | ------------------------------------ |
| id       | Long     | 否       | 品牌id                               |
| name     | String   | 否       | 品牌名称                             |
| descr    | String   | 否       | 品牌描述                             |
| imgUrl   | String   | 否       | 品牌logo图片                         |
| seq      | Int      | 否       | 排序                                 |
| status   | Int      | 否       | 状态 1:enable, 0:disable, -1:deleted |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 2.4.删除品牌

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/brand/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 否       | 品牌id   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 3.分类信息

#### 3.1.分类信息列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/category/selectPage

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                             |
| ---------- | -------- | -------- | ------------------------------------ |
| pages      | Int      | 是       | 总页数                               |
| total      | Int      | 是       | 总条数                               |
| current    | Int      | 是       | 当前显示页                           |
| size       | Int      | 是       | 每页显示条数                         |
| records    | List     | 是       | 数据列表                             |
|            |          |          | records                              |
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

#### 3.2.添加或编辑分类信息

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/category/saveOrUpdate

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                             |
| -------- | -------- | -------- | ------------------------------------ |
| id       | Long     | 否       | 分类id                               |
| shopId   | Long     | 否       | 店铺id                               |
| parentId | Long     | 否       | 父ID                                 |
| name     | String   | 否       | 分类名称                             |
| descr    | String   | 否       | 分类描述                             |
| path     | String   | 否       | 分类地址{parent_id}-{child_id},...   |
| status   | Int      | 否       | 状态 1:enable, 0:disable, -1:deleted |
| icon     | String   | 否       | 分类图标                             |
| imgUrl   | String   | 否       | 分类的显示图片                       |
| level    | Int      | 否       | 分类层级 从0开始                     |
| seq      | Int      | 否       | 排序                                 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 3.3.删除分类信息

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/category/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 否       | 分类id   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 3.4.分类信息属性列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/category/getCategoryAttrList

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明 |
| ---------- | -------- | -------- | -------- |
|            |          |          |          |
| categoryId | Long     | 否       | 分类id   |
| attrType   |          |          |          |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明               |
| ---------- | -------- | -------- | ---------------------- |
| id         | Long     | 是       | attr id                |
| name       | String   | 是       | 属性名称               |
| desc       | String   | 是       | 属性描述               |
| searchType | Int      | 是       | 0:不需要，1:需要       |
| attrType   | Int      | 是       | 0:销售属性，1:基本属性 |
| valueStr   | String   | 是       | 属性值（以/分隔）      |
| isTick     | Boolen   | 是       | 是否选中               |
| createTime | String   | 是       | 添加时间               |
| updateTime | String   | 是       | 更新时间               |

#### 3.5.分类添加属性

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/category/categoryAddAttr

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                 |
| ---------- | -------- | -------- | ------------------------ |
| categoryId | Long     | 是       | 分类id                   |
| attrIds    | String   | 是       | 属性ID（多个以逗号隔开） |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 4.物流公司

#### 4.1.物流公司列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/delivery/selectPage

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |

**返回参数：**

| 参数名称       | 参数类型 | 是否必须 | 参数说明     |
| -------------- | -------- | -------- | ------------ |
| pages          | Int      | 是       | 总页数       |
| total          | Int      | 是       | 总条数       |
| current        | Int      | 是       | 当前显示页   |
| size           | Int      | 是       | 每页显示条数 |
| records        | List     | 是       | 数据列表     |
|                |          |          | records      |
| id             | Long     | 是       | id           |
| dvyName        | String   | 是       | 物流公司名称 |
| companyHomeUrl | String   | 是       | 公司主页     |
| queryUrl       | String   | 是       | 物流查询接口 |
| createTime     | String   | 是       | 添加时间     |
| updateTime     | String   | 是       | 更新时间     |

#### 4.2.根据ID查询物流公司

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/delivery/findById

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | id       |

**返回参数：**

| 参数名称       | 参数类型 | 是否必须 | 参数说明     |
| -------------- | -------- | -------- | ------------ |
| id             | Long     | 是       | id           |
| dvyName        | String   | 是       | 物流公司名称 |
| companyHomeUrl | String   | 是       | 公司主页     |
| queryUrl       | String   | 是       | 物流查询接口 |
| createTime     | String   | 是       | 添加时间     |
| updateTime     | String   | 是       | 更新时间     |

#### 4.3.添加或编辑物流公司

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/delivery/saveOrUpdate

**请求参数：**

| 参数名称       | 参数类型 | 是否必须 | 参数说明     |
| -------------- | -------- | -------- | ------------ |
| id             | Long     | 否       | id           |
| dvyName        | String   | 是       | 物流公司名称 |
| companyHomeUrl | String   | 是       | 公司主页     |
| queryUrl       | String   | 是       | 物流查询接口 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 4.4.删除物流公司

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/delivery/saveOrUpdate

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | id       |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 5.留言

#### 5.1.留言列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/message/selectPage

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                 |
| ---------- | -------- | -------- | ------------------------ |
| pages      | Int      | 是       | 总页数                   |
| total      | Int      | 是       | 总条数                   |
| current    | Int      | 是       | 当前显示页               |
| size       | Int      | 是       | 每页显示条数             |
| records    | List     | 是       | 数据列表                 |
|            |          |          | records                  |
| id         | Long     | 是       | id                       |
| userId     | Long     | 是       | 用户ID                   |
| userName   | String   | 是       | 姓名                     |
| email      | String   | 是       | 邮箱                     |
| contact    | String   | 是       | 联系方式                 |
| content    | String   | 是       | 留言内容                 |
| reply      | String   | 是       | 留言回复                 |
| status     | Int      | 是       | 状态：0:未审核 1审核通过 |
| createTime | String   | 是       | 添加时间                 |
| updateTime | String   | 是       | 更新时间                 |

#### 5.2.根据ID查询留言

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/message/findById

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | id       |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                 |
| ---------- | -------- | -------- | ------------------------ |
| id         | Long     | 是       | id                       |
| userId     | Long     | 是       | 用户ID                   |
| userName   | String   | 是       | 姓名                     |
| email      | String   | 是       | 邮箱                     |
| contact    | String   | 是       | 联系方式                 |
| content    | String   | 是       | 留言内容                 |
| reply      | String   | 是       | 留言回复                 |
| status     | Int      | 是       | 状态：0:未审核 1审核通过 |
| createTime | String   | 是       | 添加时间                 |
| updateTime | String   | 是       | 更新时间                 |

#### 5.3.添加或编辑留言

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/message/saveOrUpdate

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                 |
| -------- | -------- | -------- | ------------------------ |
| id       | Long     | 否       | id                       |
| userId   | Long     | 是       | 用户ID                   |
| userName | String   | 是       | 姓名                     |
| email    | String   | 是       | 邮箱                     |
| contact  | String   | 是       | 联系方式                 |
| content  | String   | 是       | 留言内容                 |
| reply    | String   | 是       | 留言回复                 |
| status   | Int      | 是       | 状态：0:未审核 1审核通过 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 6.APP首页banner

#### 6.1.banner列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/indexBanner/selectPage

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                 |
| ---------- | -------- | -------- | ------------------------ |
| pages      | Int      | 是       | 总页数                   |
| total      | Int      | 是       | 总条数                   |
| current    | Int      | 是       | 当前显示页               |
| size       | Int      | 是       | 每页显示条数             |
| records    | List     | 是       | 数据列表                 |
|            |          |          | records                  |
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

#### 6.2.根据ID查询banner

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/indexBanner/findById

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | id       |

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

#### 6.3.添加或编辑banner

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/indexBanner/selectPage

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                 |
| -------- | -------- | -------- | ------------------------ |
| id       | Long     | 否       | id                       |
| shopId   | Long     | 是       | 店铺ID                   |
| imgUrl   | String   | 是       | 图片                     |
| des      | String   | 是       | 文字说明                 |
| title    | String   | 是       | 标题                     |
| link     | String   | 是       | 链接                     |
| status   | Int      | 是       | 状态                     |
| seq      | Int      | 是       | 排序                     |
| relation | Long     | 是       | 关联                     |
| type     | Int      | 是       | 类型（1、平台  2、店铺） |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 6.4.删除banner

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/indexBanner/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | id       |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 7.系统说明

#### 7.1.系统说明列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/sysExplain/selectPage

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                                                     |
| ---------- | -------- | -------- | ------------------------------------------------------------ |
| pages      | Int      | 是       | 总页数                                                       |
| total      | Int      | 是       | 总条数                                                       |
| current    | Int      | 是       | 当前显示页                                                   |
| size       | Int      | 是       | 每页显示条数                                                 |
| records    | List     | 是       | 数据列表                                                     |
|            |          |          | records                                                      |
| id         | Long     | 是       | id                                                           |
| type       | Int      | 是       | 类型（1、隐私政策 2、服务协议 <br />3、账号注销须知 4、商品信息管理规范<br />5、账号使用规范 6、支持的银行卡 <br />7、交易纠纷管理办法   8、禁售商品管理规范 <br />9、用户协议 10、商品说明） |
| title      | String   | 是       | 标题                                                         |
| content    | String   | 是       | 说明内容                                                     |
| createTime | String   | 是       | 添加时间                                                     |
| updateTime | String   | 是       | 更新时间                                                     |

#### 7.2.根据ID查询系统说明

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/sysExplain/findById

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | id       |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                                                     |
| ---------- | -------- | -------- | ------------------------------------------------------------ |
| id         | Long     | 是       | id                                                           |
| type       | Int      | 是       | 类型（1、隐私政策 2、服务协议 <br />3、账号注销须知 4、商品信息管理规范<br />5、账号使用规范 6、支持的银行卡 <br />7、交易纠纷管理办法   8、禁售商品管理规范 <br />9、用户协议 10、商品说明） |
| title      | String   | 是       | 标题                                                         |
| content    | String   | 是       | 说明内容                                                     |
| createTime | String   | 是       | 添加时间                                                     |
| updateTime | String   | 是       | 更新时间                                                     |

#### 7.3.添加或编辑系统说明

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/sysExplain/selectPage

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                                                     |
| -------- | -------- | -------- | ------------------------------------------------------------ |
| id       | Long     | 否       | id                                                           |
| type     | Int      | 是       | 类型（1、隐私政策 2、服务协议 <br />3、账号注销须知 4、商品信息管理规范<br />5、账号使用规范 6、支持的银行卡 <br />7、交易纠纷管理办法   8、禁售商品管理规范 <br />9、用户协议 10、商品说明） |
| title    | String   | 是       | 标题                                                         |
| content  | String   | 是       | 说明内容                                                     |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 7.4.删除系统说明

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/sysExplain/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 否       | id       |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 8.VIP

#### 8.1.VIP价格列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/sysVip/selectPage

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明         |
| ---------- | -------- | -------- | ---------------- |
| pages      | Int      | 是       | 总页数           |
| total      | Int      | 是       | 总条数           |
| current    | Int      | 是       | 当前显示页       |
| size       | Int      | 是       | 每页显示条数     |
| records    | List     | 是       | 数据列表         |
|            |          |          | records          |
| id         | Long     | 是       | id               |
| vipPrice   | Double   | 是       | vip价格          |
| mothNum    | Int      | 是       | 开通时长（月份） |
| createTime | String   | 是       | 添加时间         |
| updateTime | String   | 是       | 更新时间         |

#### 8.2.根据ID查询VIP信息

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/sysVip/findById

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | id       |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明         |
| ---------- | -------- | -------- | ---------------- |
| id         | Long     | 是       | id               |
| vipPrice   | Double   | 是       | vip价格          |
| mothNum    | Int      | 是       | 开通时长（月份） |
| createTime | String   | 是       | 添加时间         |
| updateTime | String   | 是       | 更新时间         |

#### 8.3.添加或编辑VIP信息

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/sysVip/saveOrUpdate

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明         |
| -------- | -------- | -------- | ---------------- |
| id       | Long     | 是       | id               |
| vipPrice | Double   | 是       | vip价格          |
| mothNum  | Int      | 是       | 开通时长（月份） |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 8.4.删除VIP信息

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/sysVip/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | id       |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 9.订单管理

#### 9.1.订单列表

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

### 10.系统公告

#### 10.1.系统公告列表

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

#### 10.2.新增或编辑系统公告

**请求说明：**HTTP POST

**请求地址：http://66.42.60.149/zuul/reception-api-cfg/sysMsg/saveOrUpdate

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明 |
| ---------- | -------- | -------- | -------- |
| id         | Long     | 否       | 消息ID   |
| title      | String   | 是       | 标题     |
| msgContent | String   | 是       | 消息内容 |
| link       | String   | 是       | 链接     |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 11.热销商品与精选商品管理

#### 11.1.商品列表

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

#### 11.2.新增或编辑热销商品或精选商品

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-comm/spuFlg/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | ID       |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 11.3.删除热销商品或精选商品

**请求说明：**HTTP POST

**请求地址：**http://66.42.60.149/zuul/reception-api-comm/spuFlg/saveOrUpdate

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                            |
| -------- | -------- | -------- | ----------------------------------- |
| id       | Long     | 否       | ID                                  |
| type     | Int      | 是       | 商品类型（1、热销商品 2、精品推荐） |
| spuId    | Long     | 是       | 商品Id                              |
| seq      | Int      | 是       | 排序                                |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 11.4.热销商品列表

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

#### 11.5.推荐商品列表

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

## 2.商家

### 1.属性

#### 1.1.属性列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attr/getAttrPagerList

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |
| shopId      | Long     | 是       | 店铺ID         |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明               |
| ---------- | -------- | -------- | ---------------------- |
| pages      | Int      | 是       | 总页数                 |
| total      | Int      | 是       | 总条数                 |
| current    | Int      | 是       | 当前显示页             |
| size       | Int      | 是       | 每页显示条数           |
| records    | List     | 是       | 数据列表               |
|            |          |          | records                |
| id         | Long     | 是       | attr id                |
| shopId     | Long     | 是       | 店铺Id                 |
| name       | String   | 是       | 属性名称               |
| desc       | String   | 是       | 属性描述               |
| searchType | Int      | 是       | 0:不需要，1:需要       |
| attrType   | Int      | 是       | 0:销售属性，1:基本属性 |
| valueStr   | String   | 是       | 属性值（以/分隔）      |
| createTime | String   | 是       | 添加时间               |
| updateTime | String   | 是       | 更新时间               |

#### 1.2.属性列表查询

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attr/getAttrList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| shopId   | Long     | 是       | 店铺ID   |
| spuId    | Long     | 否       | 商品ID   |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明               |
| ---------- | -------- | -------- | ---------------------- |
| id         | Long     | 是       | attr id                |
| shopId     | Long     | 是       | 店铺Id                 |
| name       | String   | 是       | 属性名称               |
| desc       | String   | 是       | 属性描述               |
| searchType | Int      | 是       | 0:不需要，1:需要       |
| attrType   | Int      | 是       | 0:销售属性，1:基本属性 |
| valueStr   | String   | 是       | 属性值（以/分隔）      |
| createTime | String   | 是       | 添加时间               |
| updateTime | String   | 是       | 更新时间               |
| isTick     | Boolean  | 是       | 是否选中               |

#### 1.3.添加或编辑属性

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attr/saveOrUpdate

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明               |
| ---------- | -------- | -------- | ---------------------- |
| id         | Long     | 否       | attr id                |
| shopId     | Long     | 否       | 店铺Id                 |
| name       | String   | 否       | 属性名称               |
| desc       | String   | 否       | 属性描述               |
| searchType | Int      | 否       | 0:不需要，1:需要       |
| attrType   | Int      | 否       | 0:销售属性，1:基本属性 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 1.4.删除属性

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attr/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | attr id  |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 1.5.属性值列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attrValue/getList

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| attrId   | Long     | 是       | 属性id   |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明 |
| ---------- | -------- | -------- | -------- |
| id         | Long     | 是       | 属性值id |
| attrId     | Long     | 是       | 属性id   |
| value      | String   | 是       | 属性值   |
| createTime | String   | 是       | 添加时间 |
| updateTime | String   | 是       | 更新时间 |

#### 1.6.添加或修改属性值

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attrValue/saveOrUpdate

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 否       | 属性值id |
| attrId   | Long     | 否       | 属性id   |
| value    | String   | 否       | 属性值   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 1.7.删除属性值

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/attrValue/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | 属性值id |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 2.分类信息

#### 2.1.分类信息列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/category/selectPage

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |
| shopId      | Long     | 否       | 店铺ID         |
| parentId    | Long     | 否       | 父级ID         |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                             |
| ---------- | -------- | -------- | ------------------------------------ |
| pages      | Int      | 是       | 总页数                               |
| total      | Int      | 是       | 总条数                               |
| current    | Int      | 是       | 当前显示页                           |
| size       | Int      | 是       | 每页显示条数                         |
| records    | List     | 是       | 数据列表                             |
|            |          |          | records                              |
| id         | Long     | 是       | 分类id                               |
| shopId     | Long     | 是       | 店铺id                               |
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

#### 2.2.添加或编辑分类信息

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/category/saveOrUpdate

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                             |
| -------- | -------- | -------- | ------------------------------------ |
| id       | Long     | 否       | 分类id                               |
| shopId   | Long     | 否       | 店铺id                               |
| parentId | Long     | 否       | 父ID                                 |
| name     | String   | 否       | 分类名称                             |
| descr    | String   | 否       | 分类描述                             |
| path     | String   | 否       | 分类地址{parent_id}-{child_id},...   |
| status   | Int      | 否       | 状态 1:enable, 0:disable, -1:deleted |
| icon     | String   | 否       | 分类图标                             |
| imgUrl   | String   | 否       | 分类的显示图片                       |
| level    | Int      | 否       | 分类层级 从0开始                     |
| seq      | Int      | 否       | 排序                                 |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 2.3.删除分类信息

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/category/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 否       | 分类id   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 2.4.分类信息属性列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/category/getCategoryAttrList

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明 |
| ---------- | -------- | -------- | -------- |
| categoryId | Long     | 否       | 分类id   |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明               |
| ---------- | -------- | -------- | ---------------------- |
| id         | Long     | 是       | attr id                |
| shopId     | Long     | 是       | 店铺Id                 |
| name       | String   | 是       | 属性名称               |
| desc       | String   | 是       | 属性描述               |
| searchType | Int      | 是       | 0:不需要，1:需要       |
| attrType   | Int      | 是       | 0:销售属性，1:基本属性 |
| valueStr   | String   | 是       | 属性值（以/分隔）      |
| isTick     | Boolen   | 是       | 是否选中               |
| createTime | String   | 是       | 添加时间               |
| updateTime | String   | 是       | 更新时间               |

#### 2.5.分类添加属性

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/category/categoryAddAttr

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                 |
| ---------- | -------- | -------- | ------------------------ |
| categoryId | Long     | 是       | 分类id                   |
| attrIds    | String   | 是       | 属性ID（多个以逗号隔开） |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 2.6.分类信息属性列表层级

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/category/getCategoryAttrLists

**请求参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明 |
| ---------- | -------- | -------- | -------- |
| categoryId | Long     | 是       | 分类id   |
| spuId      | Long     | 否       | 商品id   |

**返回参数：**

| 参数名称      | 参数类型 | 是否必须 | 参数说明               |
| ------------- | -------- | -------- | ---------------------- |
| id            | Long     | 是       | attr id                |
| shopId        | Long     | 是       | 店铺Id                 |
| name          | String   | 是       | 属性名称               |
| desc          | String   | 是       | 属性描述               |
| searchType    | Int      | 是       | 0:不需要，1:需要       |
| attrType      | Int      | 是       | 0:销售属性，1:基本属性 |
| valueStr      | String   | 是       | 属性值（以/分隔）      |
| createTime    | String   | 是       | 添加时间               |
| updateTime    | String   | 是       | 更新时间               |
| attrValueList | List     | 是       | 属性列表               |
|               |          |          | attrValueList          |
| id            | Long     | 是       | 属性值id               |
| attrId        | Long     | 是       | 属性id                 |
| value         | String   | 是       | 属性值                 |
| createTime    | String   | 是       | 添加时间               |
| updateTime    | String   | 是       | 更新时间               |
| isTick        | Boolean  | 是       | 是否选中               |

### 3.商品

#### 3.1.商品列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/spu/selectPage

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |
| shopId      | Long     | 是       | 店铺ID         |

**返回参数：**

| 参数名称       | 参数类型 | 是否必须 | 参数说明                     |
| -------------- | -------- | -------- | ---------------------------- |
| pages          | Int      | 是       | 总页数                       |
| total          | Int      | 是       | 总条数                       |
| current        | Int      | 是       | 当前显示页                   |
| size           | Int      | 是       | 每页显示条数                 |
| records        | List     | 是       | 数据列表                     |
|                |          |          | records                      |
| id             | Long     | 是       | spu id                       |
| shopId         | Long     | 是       | 店铺id                       |
| brandId        | Long     | 是       | 品牌ID                       |
| categoryId     | Long     | 是       | 分类ID                       |
| shopCategoryId | Long     | 是       | 店铺分类ID                   |
| name           | String   | 是       | 商品名称                     |
| sellingPoint   | String   | 是       | 卖点                         |
| mainImgUrl     | String   | 是       | 商品介绍主图                 |
| imgUrls        | String   | 是       | 商品图片 多个图片逗号分隔    |
| video          | String   | 是       | 商品视频                     |
| priceFee       | Long     | 是       | 售价，整数方式保存           |
| marketPriceFee | Long     | 是       | 市场价，整数方式保存         |
| status         | Int      | 是       | 状态 -1:删除, 0:下架, 1:上架 |
| hasSkuImg      | Int      | 是       | sku是否含有图片 0无 1有      |
| seq            | Int      | 是       | 序号                         |
| createTime     | String   | 是       | 添加时间                     |
| updateTime     | String   | 是       | 更新时间                     |
| saleNum        | Long     | 是       | 销量                         |
| actualStock    | Long     | 是       | 库存                         |

#### 3.2.发布或编辑商品

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/spu/saveOrUpdateSpu

**请求参数：**

| 参数名称       | 参数类型 | 是否必须 | 参数说明                  |
| -------------- | -------- | -------- | ------------------------- |
| id             | Long     | 否       | spu id                    |
| shopId         | Long     | 是       | 店铺id                    |
| brandId        | Long     | 是       | 品牌ID                    |
| categoryId     | Long     | 是       | 分类ID                    |
| shopCategoryId | Long     | 是       | 店铺分类ID                |
| name           | String   | 是       | 商品名称                  |
| sellingPoint   | String   | 是       | 卖点                      |
| mainImgUrl     | String   | 是       | 商品介绍主图              |
| imgUrls        | String   | 是       | 商品图片 多个图片逗号分隔 |
| video          | String   | 是       | 商品视频                  |
| priceFee       | Long     | 是       | 售价，整数方式保存        |
| marketPriceFee | Long     | 是       | 市场价，整数方式保存      |
| hasSkuImg      | Int      | 是       | sku是否含有图片 0无 1有   |
| seq            | Int      | 是       | 序号                      |
| actualStock    | Int      | 是       | 实际库存                  |
| basicAttrList  | List     | 是       | 平台属性列表              |
|                |          |          | basicAttrList             |
| id             | Long     | 是       | attr id                   |
| name           | String   | 是       | 属性名称                  |
| attrValueList  | List     | 是       | 属性值列表                |
|                |          |          | attrValueList             |
| id             | Long     | 是       | 属性值id                  |
| value          | String   | 是       | 属性值                    |
|                |          |          |                           |
| saleAttrList   | List     | 是       | 销售属性列表              |
|                |          |          | basicAttrList             |
| id             | Long     | 是       | attr id                   |
| name           | String   | 是       | 属性名称                  |
| attrValueList  | List     | 是       | 属性值列表                |
|                |          |          | attrValueList             |
| id             | Long     | 是       | 属性值id                  |
| value          | String   | 是       | 属性值                    |
|                |          |          |                           |
| skuList        | List     | 是       | 商品列表                  |
|                |          |          | skuList                   |
| skuName        | String   | 是       | sku名称                   |
| imgUrl         | String   | 是       | 商品图片                  |
| priceFee       | Long     | 是       | 售价，整数方式保存        |
| marketPriceFee | Long     | 是       | 市场价，整数方式保存      |
| partyCode      | String   | 是       | 商品编码                  |
| modelId        | String   | 是       | 商品条形码                |
| weight         | Double   | 是       | 商品重量                  |
| volume         | Double   | 是       | 商品体积                  |
|                |          |          |                           |
| spuDetail      | Object   | 是       | 商品详情                  |
|                |          |          | spuDetail                 |
| detail         | String   | 是       | 商品详情                  |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 3.3.根据商品ID查询商品详情

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/spu/findById

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 否       | 商品ID   |

**返回参数：**

| 参数名称       | 参数类型 | 是否必须 | 参数说明                  |
| -------------- | -------- | -------- | ------------------------- |
| id             | Long     | 否       | spu id                    |
| shopId         | Long     | 是       | 店铺id                    |
| brandId        | Long     | 是       | 品牌ID                    |
| categoryId     | Long     | 是       | 分类ID                    |
| shopCategoryId | Long     | 是       | 店铺分类ID                |
| name           | String   | 是       | 商品名称                  |
| sellingPoint   | String   | 是       | 卖点                      |
| mainImgUrl     | String   | 是       | 商品介绍主图              |
| imgUrls        | String   | 是       | 商品图片 多个图片逗号分隔 |
| video          | String   | 是       | 商品视频                  |
| priceFee       | Long     | 是       | 售价，整数方式保存        |
| marketPriceFee | Long     | 是       | 市场价，整数方式保存      |
| hasSkuImg      | Int      | 是       | sku是否含有图片 0无 1有   |
| seq            | Int      | 是       | 序号                      |
| actualStock    | Int      | 是       | 实际库存                  |
| basicAttrList  | List     | 是       | 平台属性列表              |
|                |          |          | basicAttrList             |
| id             | Long     | 是       | attr id                   |
| name           | String   | 是       | 属性名称                  |
| attrValueList  | List     | 是       | 属性值列表                |
|                |          |          | attrValueList             |
| id             | Long     | 是       | 属性值id                  |
| value          | String   | 是       | 属性值                    |
| isTick         | Boolean  | 是       | 是否选中                  |
|                |          |          |                           |
| saleAttrList   | List     | 是       | 销售属性列表              |
|                |          |          | basicAttrList             |
| id             | Long     | 是       | attr id                   |
| name           | String   | 是       | 属性名称                  |
| isTick         | Boolean  | 是       | 是否选中                  |
| attrValueList  | List     | 是       | 属性值列表                |
|                |          |          | attrValueList             |
| id             | Long     | 是       | 属性值id                  |
| value          | String   | 是       | 属性值                    |
| isTick         | Boolean  | 是       | 是否选中                  |
|                |          |          |                           |
| skuList        | List     | 是       | 商品列表                  |
|                |          |          | skuList                   |
| skuName        | String   | 是       | sku名称                   |
| imgUrl         | String   | 是       | 商品图片                  |
| priceFee       | Long     | 是       | 售价，整数方式保存        |
| marketPriceFee | Long     | 是       | 市场价，整数方式保存      |
| partyCode      | String   | 是       | 商品编码                  |
| modelId        | String   | 是       | 商品条形码                |
| weight         | Double   | 是       | 商品重量                  |
| volume         | Double   | 是       | 商品体积                  |
|                |          |          |                           |
| spuDetail      | Object   | 是       | 商品详情                  |
|                |          |          | spuDetail                 |
| detail         | String   | 是       | 商品详情                  |

#### 3.3.删除商品

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/spu/logicalDelete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | 商品id   |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 3.4.上架或下架商品

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/spu/onOrShelf

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                |
| -------- | -------- | -------- | ----------------------- |
| id       | Long     | 是       | 商品id                  |
| type     | Int      | 是       | 类型（1、上架 2、下架） |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 3.5.批量上架或下架商品

**请求说明：**HTTP POST

**请求地址：**/backstage-api-comm/spu/onOrShelfs

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                 |
| -------- | -------- | -------- | ------------------------ |
| ids      | String   | 是       | 商品id（多个以逗号隔开） |
| type     | Int      | 是       | 类型（1、上架 2、下架）  |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 4.店铺首页banner

#### 4.1.banner列表

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/indexBanner/selectPage

**请求参数：**

| 参数名称    | 参数类型 | 是否必须 | 参数说明       |
| ----------- | -------- | -------- | -------------- |
| currentPage | Int      | 是       | 显示第几页     |
| pageSize    | Int      | 是       | 每页显示多少条 |
| shopId      | Long     | 是       | 店铺ID         |

**返回参数：**

| 参数名称   | 参数类型 | 是否必须 | 参数说明                 |
| ---------- | -------- | -------- | ------------------------ |
| pages      | Int      | 是       | 总页数                   |
| total      | Int      | 是       | 总条数                   |
| current    | Int      | 是       | 当前显示页               |
| size       | Int      | 是       | 每页显示条数             |
| records    | List     | 是       | 数据列表                 |
|            |          |          | records                  |
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

#### 4.2.根据ID查询banner

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/indexBanner/findById

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | id       |

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

#### 4.3.添加或编辑banner

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/indexBanner/saveOrUpdate

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明                 |
| -------- | -------- | -------- | ------------------------ |
| id       | Long     | 否       | id                       |
| shopId   | Long     | 是       | 店铺ID                   |
| imgUrl   | String   | 是       | 图片                     |
| des      | String   | 是       | 文字说明                 |
| title    | String   | 是       | 标题                     |
| link     | String   | 是       | 链接                     |
| status   | Int      | 是       | 状态                     |
| seq      | Int      | 是       | 排序                     |
| relation | Long     | 是       | 关联                     |
| type     | Int      | 是       | 类型（1、平台  2、店铺） |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

#### 4.4.删除banner

**请求说明：**HTTP POST

**请求地址：**/backstage-api-cfg/indexBanner/delete

**请求参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
| id       | Long     | 是       | id       |

**返回参数：**

| 参数名称 | 参数类型 | 是否必须 | 参数说明 |
| -------- | -------- | -------- | -------- |
|          | boolean  | 是       | 是否成功 |

### 5.订单管理

#### 5.1.订单列表

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
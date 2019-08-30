# BISS API Reference v0.01

> 当前文档不包含API鉴权内容，以及和此相关的UID识别问题



# Assets

## Assets

### HTTP Request

```http
GET /api/v1/assets/assets
```

### Response

| Code                                | Description |
| ----------------------------------- | ----------- |
| 200<br />[*AssetsResp*](#AssetsResp) | 资产列表    |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/api/v1/assets/assets'
```

**curl response**

```json
{
    "btcValue": "0.0",
    "legalCurrency": "CU_USD",
    "legalValue": "0.0",
    "assets": [
        {
            "symbol": "BTC",
            "name": "Bitcoin",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": ""
        },
        {
            "symbol": "ETH",
            "name": "Ethereum",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": ""
        },
        {
            "symbol": "EOS",
            "name": "EOS",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": ""
        },
        {
            "symbol": "BCH",
            "name": "Bitcoin Cash",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": ""
        },
        {
            "symbol": "LTC",
            "name": "Litecoin",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": ""
        },
        {
            "symbol": "ETC",
            "name": "Ethereum Classic",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": ""
        },
        {
            "symbol": "IOST",
            "name": "IOST",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": ""
        },
        {
            "symbol": "USDT",
            "name": "Tether",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": ""
        }
    ]
}
```



# Trade

## Entrust

### HTTP Request

```http
POST /api/v1/trade/{symbol}/{market}
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

**Body Parameters**

| Parameter                               | Description |
| --------------------------------------- | ----------- |
| `body`<br />[*EntrustReq*](#EntrustReq) | 委托请求    |

### Response

| Code                                   | Description |
| -------------------------------------- | ----------- |
| 200<br />[*EntrustResp*](#EntrustResp) | 委托应答    |

### Example

**curl request**

```shell
curl -X POST -d '
{
	"type": "OT_LIMIT",
	"side": "TS_BID",
	"price": "1.2",
	"qty": "3.4"
}' $BISS_SERVER'/api/v1/trade/BTC/USDT'
```

**curl response**

```json
{
    "oid": "10"
}
```



## Cancel

### HTTP Request

```http
DELETE /api/v1/trade/{symbol}/{market}/{oid}
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |
| `oid`<br />*string*    | 订单id      |

### Response

| Code | Description |
| ---- | ----------- |
| 200  | 撤单应答    |

### Example

**curl request**

```shell
curl -X DELETE $BISS_SERVER'/api/v1/trade/BTC/USDT/10'
```

**curl response**

```json
{}
```



## BatchCancel

### HTTP Request

```http
DELETE /api/v1/trade/{symbol}/{market}
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

### Response

| Code                                           | Description  |
| ---------------------------------------------- | ------------ |
| 200<br />[*BatchCancelResp*](#BatchCancelResp) | 批量撤单应答 |

### Example

**curl request**

```shell
curl -X DELETE $BISS_SERVER'/api/v1/trade/BTC/USDT'
```

**curl response**

```json
{
    "total": 5,
    "done": 5
}
```



## EntrustList

### HTTP Request

```http
GET /api/v1/trade/{symbol}/{market}
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

**Query Parameters**

| Parameter                                                  | Description     |
| ---------------------------------------------------------- | --------------- |
| `order_list_type`<br />[*OrderListType*](#OrderListType)   | 订单列表类型    |
| `sort_type`<br />[*OrderListSortType*](#OrderListSortType) | 订单列表排序    |
| `sort_direction`<br />[*SortDirection*](#SortDirection)    | 排序方向        |
| `page`<br />*string*                                       | 页号（从1开始） |
| `page_size`<br />*string*                                  | 每页大小        |

### Response

| Code                                       | Description  |
| ------------------------------------------ | ------------ |
| 200<br />[*OrderListResp*](#OrderListResp) | 订单列表应答 |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/api/v1/trade/BTC/USDT?order_list_type=OLT_CURRENT&sort_type=TIME&sort_direction=SD_DESC&page=1&page_size=50'
```

**curl response**

```json
{
    "total": 3,
    "page": 1,
    "hasMore": false,
    "sortDirection": "SD_DESC",
    "sortType": "TIME",
    "orders": [
        {
            "id": "27",
            "type": "OT_LIMIT",
            "side": "TS_BID",
            "price": "0.1719",
            "qty": "3",
            "amount": "0.5157",
            "status": "OS_OPEN",
            "filled": "0",
            "left": "0.5157",
            "time": "1541585893603",
            "ticker": {
                "symbol": "BTC",
                "market": "USDT"
            },
            "filledAvg": "",
            "fee": "[FM_PROPORTIONAL: 0.001]"
        },
        {
            "id": "26",
            "type": "OT_LIMIT",
            "side": "TS_BID",
            "price": "0.1719",
            "qty": "2",
            "amount": "0.3438",
            "status": "OS_OPEN",
            "filled": "0",
            "left": "0.3438",
            "time": "1541585890620",
            "ticker": {
                "symbol": "BTC",
                "market": "USDT"
            },
            "filledAvg": "",
            "fee": "[FM_PROPORTIONAL: 0.001]"
        },
        {
            "id": "25",
            "type": "OT_LIMIT",
            "side": "TS_BID",
            "price": "0.1719",
            "qty": "1",
            "amount": "0.1719",
            "status": "OS_OPEN",
            "filled": "0",
            "left": "0.1719",
            "time": "1541585342096",
            "ticker": {
                "symbol": "BTC",
                "market": "USDT"
            },
            "filledAvg": "",
            "fee": "[FM_PROPORTIONAL: 0.001]"
        }
    ]
}
```



# Quote

## RealTime

### HTTP Request

```http
GET /api/v1/quote/{symbol}/{market}/realtime
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

### Response

| Code                                         | Description  |
| -------------------------------------------- | ------------ |
| 200<br />[*RealTimeUpdate*](#RealTimeUpdate) | 实时行情应答 |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/api/v1/quote/BTC/USDT/realtime'
```

**curl response**

```json
{
    "ticker": {
        "symbol": "BTC",
        "market": "USDT"
    },
    "price": "2.5",
    "h24": {
        "open": "1",
        "close": "2.5",
        "volume": "45.5",
        "change": "1.5",
        "ratio": "150.0000",
        "high": "3",
        "low": "1",
        "amount": "45.5",
        "avg": "1.00000000"
    },
    "tickTime": "1541648245778",
    "quoteTime": "1541648245778",
    "cirulatingSupply": "17365137.00",
    "maxSupply": "21000000.00"
}
```



## TickHistory

### HTTP Request

```http
GET /api/v1/quote/{symbol}/{market}/tick-history
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

**Query Parameters**

| Parameter             | Description                                                  |
| --------------------- | ------------------------------------------------------------ |
| `start`<br />*string* | 从此时间向前获取（取值为1970.1.1UTC距今的毫秒数，0表示当前时间） |
| `count`<br />*string* | 条数                                                         |

### Response

| Code                                           | Description      |
| ---------------------------------------------- | ---------------- |
| 200<br />[*TickHistoryResp*](#TickHistoryResp) | 逐笔历史数据应答 |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/api/v1/quote/BTC/USDT/tick-history?start=1541648245778&count=50'
```

**curl response**

```json
{
    "ticker": {
        "symbol": "BTC",
        "market": "USDT"
    },
    "start": "50",
    "count": 5,
    "ticks": [
        {
            "id": "5",
            "time": "1541648205148",
            "price": "2.5",
            "volume": "5",
            "amount": "12.5",
            "side": "TS_ASK",
            "bidOrderNo": "0",
            "bidOrderQty": "0",
            "askOrderNo": "0",
            "askOrderQty": "0"
        },
        {
            "id": "4",
            "time": "1541648152417",
            "price": "3",
            "volume": "5",
            "amount": "15",
            "side": "TS_BID",
            "bidOrderNo": "0",
            "bidOrderQty": "0",
            "askOrderNo": "0",
            "askOrderQty": "0"
        },
        {
            "id": "3",
            "time": "1541648112185",
            "price": "3",
            "volume": "5",
            "amount": "15",
            "side": "TS_BID",
            "bidOrderNo": "0",
            "bidOrderQty": "0",
            "askOrderNo": "0",
            "askOrderQty": "0"
        },
        {
            "id": "2",
            "time": "1541648067465",
            "price": "2",
            "volume": "1",
            "amount": "2",
            "side": "TS_BID",
            "bidOrderNo": "0",
            "bidOrderQty": "0",
            "askOrderNo": "0",
            "askOrderQty": "0"
        },
        {
            "id": "1",
            "time": "1541648052326",
            "price": "1",
            "volume": "1",
            "amount": "1",
            "side": "TS_BID",
            "bidOrderNo": "0",
            "bidOrderQty": "0",
            "askOrderNo": "0",
            "askOrderQty": "0"
        }
    ]
}
```



## Position

### HTTP Request

```http
GET /api/v1/quote/{symbol}/{market}/position
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

**Query Parameters**

| Parameter             | Description  |
| --------------------- | ------------ |
| `merge`<br />*string* | 盘口合并深度 |

### Response

| Code                                         | Description |
| -------------------------------------------- | ----------- |
| 200<br />[*PositionUpdate*](#PositionUpdate) | 盘口应答    |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/api/v1/quote/BTC/USDT/position?merge=0.001'
```

**curl response**

```json

```



# DATA REFERENCE

## DATA TYPE

### AssetsResp

| Field                                         | Description |
| --------------------------------------------- | ----------- |
| `btc_value`<br />*string*                     | BTC 估值    |
| `legal_currency`<br />[*Currency*](#Currency) | 法币类型    |
| `legal_value`<br />*string*                   | 法币估值    |
| `assets`<br />[*Asset*](#Asset) array         | 资产列表    |

### Asset

| Field                     | Description |
| ------------------------- | ----------- |
| `symbol`<br />*string*    | 标的        |
| `name`<br />*string*      | 名称        |
| `amount`<br />*string*    | 总额        |
| `available`<br />*string* | 可用        |
| `frozen`<br />*string*    | 冻结        |
| `btc_value`<br />*string* | BTC 估值    |

### EntrustReq

| Field                                 | Description |
| ------------------------------------- | ----------- |
| `type`<br />[*OrderType*](#OrderType) | 订单类型    |
| `side`<br />[*TradeSide*](#TradeSide) | 方向        |
| `price`<br />*string*                 | 价格        |
| `qty`<br />*string*                   | 委托数量    |

### EntrustResp

| Field               | Description |
| ------------------- | ----------- |
| `oid`<br />*string* | 订单id      |

### BatchCancelResp

| Field                 | Description  |
| --------------------- | ------------ |
| `total`<br />*string* | 当前订单总数 |
| `done`<br />*string*  | 成功撤单数   |

### OrderListResp

| Field                                                      | Description      |
| ---------------------------------------------------------- | ---------------- |
| `total`<br />*string*                                      | 订单总数         |
| `page`<br />*string*                                       | 页号             |
| `has_more`<br />*string*                                   | 是否还有更多数据 |
| `sort_direction`<br />[*SortDirection*](#SortDirection)    | 排序方向         |
| `sort_type`<br />[*OrderListSortType*](#OrderListSortType) | 订单列表排序     |
| `orders`<br />[*Order*](#Order) array                      | 订单信息         |

### Order

| Field                                       | Description |
| ------------------------------------------- | ----------- |
| `id`<br />*string*                          | 订单id      |
| `type`<br />[*OrderType*](#OrderType)       | 订单类型    |
| `side`<br />[*TradeSide*](#TradeSide)       | 方向        |
| `price`<br />*string*                       | 价格        |
| `qty`<br />*string*                         | 委托数量    |
| `amount`<br />*string*                      | 市值        |
| `status`<br />[*OrderStatus*](#OrderStatus) | 订单状态    |
| `filled`<br />*string*                      | 已成交      |
| `left`<br />*string*                        | 未成交      |
| `time`<br />*string*                        | 委托时间    |
| `ticker`<br />[*Ticker*](#Ticker)           | 交易对      |
| `filled_avg`<br />*string*                  | 成交均价    |
| `fee`<br />*string*                         | 手续费      |

### Ticker

| Field                  | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

### RealTimeUpdate

| Field                                  | Description                    |
| -------------------------------------- | ------------------------------ |
| `ticker`<br />[*Ticker*](#Ticker)      | 交易对                         |
| `price`<br />*string*                  | 现价                           |
| `h24`<br />[*PeroidData*](#PeroidData) | 24小时数据                     |
| `tick_time`<br />*string*              | 最新的tick的时间               |
| `quote_time`<br />*string*             | tick时间对应的行情服务器的时间 |
| `cirulating_supply`<br />*string*      | 当前流通量                     |
| `max_supply`<br />*string*             | 总发行量                       |

### PeroidData

| Field                  | Description |
| ---------------------- | ----------- |
| `open`<br />*string*   | 开盘价      |
| `close`<br />*string*  | 收盘价      |
| `volume`<br />*string* | 成交量      |
| `change`<br />*string* | 涨跌价      |
| `ratio`<br />*string*  | 涨跌幅      |
| `high`<br />*string*   | 最高价      |
| `low`<br />*string*    | 最低价      |
| `amount`<br />*string* | 成交额      |
| `avg`<br />*string*    | 均价        |

### TickHistoryResp

| Field                                      | Description                                       |
| ------------------------------------------ | ------------------------------------------------- |
| `ticker`<br />[*Ticker*](#Ticker)          | 交易对                                            |
| `start`<br />*string*                      | 从此时间向前获取（取值为1970.1.1UTC距今的毫秒数） |
| `count`<br />*string*                      | 条数                                              |
| `ticks`<br />[*TickData*](#TickData) array | tick数据                                          |

### TickData
| Field                                 | Description |
| ------------------------------------- | ----------- |
| `id`<br />*string*                    | tick序号    |
| `time`<br />*string*                  | 成交时间    |
| `price`<br />*string*                 | 成交价格    |
| `volume`<br />*string*                | 成交数量    |
| `amount`<br />*string*                | 成交额      |
| `side`<br />[*TradeSide*](#TradeSide) | 方向        |
| `bid_order_no`<br />*string*          | 买单编号    |
| `bid_order_qty`<br />*string*         | 买单数量    |
| `ask_order_no`<br />*string*          | 卖单编号    |
| `ask_order_qty`<br />*string*         | 卖单数量    |


### PositionUpdate
| Field                                                        | Description  |
| ------------------------------------------------------------ | ------------ |
| `ticker`<br />[*Ticker*](#Ticker)                            | 交易对       |
| `merge`<br />*string*                                        | 盘口合并深度 |
| `items`<br />[*PositionUpdateItem*](#PositionUpdateItem) array | 盘口更新项   |

### PositionUpdateItem

| Field                                             | Description |
| ------------------------------------------------- | ----------- |
| `mode`<br />[*UpdateMode*](#UpdateMode)           | 更新模式    |
| `bids`<br />[*PositionData*](#PositionData) array | 买盘口数据  |
| `asks`<br />[*PositionData*](#PositionData) array | 卖盘口数据  |

### PositionData

| Field                           | Description        |
| ------------------------------- | ------------------ |
| `level`<br />*string*           | 盘口深度           |
| `price`<br />*string*           | 价格               |
| `volume`<br />*string*          | 数量               |
| `amount`<br />*string*          | 市值               |
| `order_qty`<br />*string* array | 当前报价的委托队列 |



## STRING ENUM

### Currency

| Value  | Description |
| ------ | ----------- |
| CU_CNY | 人民币      |
| CU_USD | 美元        |
| CU_HKD | 港币        |

### OrderType

| Value     | Description |
| --------- | ----------- |
| OT_LIMIT  | 限价单      |
| OT_MARKET | 市价单      |

### TradeSide

| Value  | Description |
| ------ | ----------- |
| TS_BID | 买单        |
| TS_ASK | 卖单        |

### OrderListType

| Value       | Description    |
| ----------- | -------------- |
| OLT_CURRENT | 当前订单       |
| OLT_HISTORY | 历史订单       |
| OLT_24HOURS | 24小时成交订单 |
| OLT_DETAILS | 成交订单       |

### OrderListSortType

| Value  | Description |
| ------ | ----------- |
| TIME   | 时间        |
| STATUS | 状态        |

### SortDirection

| Value   | Description |
| ------- | ----------- |
| SD_AESC | 升序        |
| SD_DESC | 降序        |

### OrderStatus

| Value       | Description |
| ----------- | ----------- |
| OS_OPEN     | 待成交      |
| OS_CLOSED   | 全部成交    |
| OS_CANCELED | 已取消      |
| OS_EXPIRED  | 已过期      |
| OS_INVALID  | 废单        |

### UpdateMode

| Value       | Description |
| ----------- | ----------- |
| UM_OVERRIDE | 全局覆盖    |
| UM_MODIFY   | 修改        |
| UM_ADD      | 添加        |
| UM_DELETE   | 删除        |



## ERROR CODE

> 系统通过HTTP Response header返回错误码，KEY是`code`，取值和说明如下： 

| Value | Description                    |
| ----- | ------------------------------ |
| 0     | 成功                           |
| 10001 | 参数出错                       |
| 10002 | 请输入正确的电子邮件地址       |
| 10003 | 请输入正确的手机号码           |
| 10004 | 邮箱验证码格式错误，请重新输入 |
| 10005 | 手机验证码格式错误，请重新输入 |
| 10006 | GA验证码格式错误，请重新输入   |
| 10007 | 签名数据有误                   |
| 10008 | 验证场景不存在                 |
| 10009 | 不支持的验证方式               |
| 20001 | 用户不存在                     |
| 20002 | 邮箱已注册                     |
| 20003 | 账号或密码错误,请重新输入      |
| 20004 | 需要验证                       |
| 20005 | 用户已绑定手机                 |
| 20006 | 手机号已被其他用户绑定         |
| 20007 | 密码不正确                     |
| 20008 | 密码签名校验错误               |
| 20009 | Google 验证码已经绑定          |
| 20010 | Google 验证码错误              |
| 20012 | 邮箱验证码错误                 |
| 20013 | 手机验证码错误                 |
| 20015 | KYC 生成文件上传信息出错       |
| 20016 | Parse KYC 文件 URL 失败        |
| 30001 | 市场不存在                     |
| 40001 | 不支持的数字货币               |
| 40002 | 提币地址不存在                 |
| 40003 | 余额不足                       |
| 40004 | 单次提币小于最小限制           |
| 40005 | 单次提币小于最小限制           |
| 40006 | 生成地址失败                   |
| 40007 | 不支持的地址生成               |
| 70001 | Ticker 不存在                  |
| 70002 | 订单类型错误                   |
| 70003 | 交易方向错误                   |
| 70004 | 价格小于最小交易价格           |
| 70005 | 数量小于最小交易单位           |
| 70006 | 价格精度溢出                   |
| 70007 | 数量精度溢出                   |
| 70008 | ME 请求发送失败                |
| 70009 | ME 请求超时                    |
| 70010 | ME Message 格式错误            |
| 70011 | 订单编号为 0                   |
| 70012 | 订单编号不存在                 |
| 70013 | 订单无法被取消                 |
| 80001 | 委托参数错误                   |
| 80002 | 取消委托参数错误               |
| 80003 | 修改委托参数错误               |
| 80004 | 内部状态错误                   |
| 80005 | 订单编号不存在                 |
| 80006 | 价格列表不存在                 |
| 90002 | 数据库操作错误                 |
| 90003 | 总线错误                       |
| 90004 | GA 错误                        |
| 90005 | HSM 错误                       |


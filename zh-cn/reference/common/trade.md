


 <!-- end services -->


# 数据对象



## Market




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| market | [string](#string) |  | 市场 |




## Symbol




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 符号 |




## Ticker




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 符号 |
| market | [string](#string) |  | 市场 |


 <!-- end messages -->

# 枚举类型


<a name="biss.common.trade.Board"></a>

## Board
交易板块

| Name | Number | Description |
| ---- | ------ | ----------- |
| MAIN | 0 | 主板 |
| GEM | 1 | 创新板 |



<a name="biss.common.trade.Category"></a>

## Category
标的类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| COIN | 0 | 数字货币 |
| STOCK | 1 | 股票 |
| FUND | 2 | 基金 |



<a name="biss.common.trade.OrderFillStatus"></a>

## OrderFillStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| OFS_NONE | 0 |  |
| OFS_UNFILLED | 1 | 待成交 |
| OFS_PARTIAL_FILLED | 2 | 部分成交 |
| OFS_FULL_FILLED | 3 | 全部成交 |



<a name="biss.common.trade.OrderListType"></a>

## OrderListType


| Name | Number | Description |
| ---- | ------ | ----------- |
| OLT_CURRENT | 0 |  |
| OLT_HISTORY | 1 |  |
| OLT_24HOURS | 2 |  |
| OLT_DETAILS | 3 |  |



<a name="biss.common.trade.OrderStatus"></a>

## OrderStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| OS_NONE | 0 |  |
| OS_OPEN | 1 | 待成交 |
| OS_CLOSED | 2 | 全部成交 |
| OS_CANCELED | 3 | 已取消 |
| OS_EXPIRED | 4 | 已过期 |
| OS_INVALID | 5 | 废单 |



<a name="biss.common.trade.OrderType"></a>

## OrderType


| Name | Number | Description |
| ---- | ------ | ----------- |
| OT_NONE | 0 |  |
| OT_LIMIT | 1 | 限价单 |
| OT_MARKET | 2 | 市价单 |



<a name="biss.common.trade.SubCategory"></a>

## SubCategory
标的类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| SC_NONE | 0 |  |
| SC_US_STOCK | 1 | 美股 |
| SC_CRYPTO_ETF | 2 | 数字货币 ETF 基金 |



<a name="biss.common.trade.TickListType"></a>

## TickListType


| Name | Number | Description |
| ---- | ------ | ----------- |
| TLT_HISTORY | 0 |  |
| TLT_24HOURS | 1 |  |



<a name="biss.common.trade.TradeSide"></a>

## TradeSide


| Name | Number | Description |
| ---- | ------ | ----------- |
| TS_NONE | 0 |  |
| TS_BID | 1 | 买单 |
| TS_ASK | 2 | 卖单 |



<a name="biss.common.trade.TradeType"></a>

## TradeType


| Name | Number | Description |
| ---- | ------ | ----------- |
| TT_NONE | 0 |  |



<a name="biss.common.trade.TradingStatus"></a>

## TradingStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| TS_NORMAL | 0 | 正常交易 |
| TS_BREAK | 1 | 休市 |
| TS_SUSPENDED | 2 | 暂停交易 |
| TS_VOL_CTR | 3 | 波动中断(Volatility Control) |


 <!-- end enums -->




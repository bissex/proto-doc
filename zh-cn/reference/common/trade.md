# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/common/trade.proto](#proto/common/trade.proto)
    - [Market](#biss.common.trade.Market)
    - [Symbol](#biss.common.trade.Symbol)
    - [Ticker](#biss.common.trade.Ticker)
  
    - [Board](#biss.common.trade.Board)
    - [Category](#biss.common.trade.Category)
    - [OrderFillStatus](#biss.common.trade.OrderFillStatus)
    - [OrderListType](#biss.common.trade.OrderListType)
    - [OrderStatus](#biss.common.trade.OrderStatus)
    - [OrderType](#biss.common.trade.OrderType)
    - [SubCategory](#biss.common.trade.SubCategory)
    - [TickListType](#biss.common.trade.TickListType)
    - [TradeSide](#biss.common.trade.TradeSide)
    - [TradeType](#biss.common.trade.TradeType)
    - [TradingStatus](#biss.common.trade.TradingStatus)
  
  
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/common/trade.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/common/trade.proto



<a name="biss.common.trade.Market"></a>

### Market



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| market | [string](#string) |  | 市场 |






<a name="biss.common.trade.Symbol"></a>

### Symbol



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 符号 |






<a name="biss.common.trade.Ticker"></a>

### Ticker



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 符号 |
| market | [string](#string) |  | 市场 |





 


<a name="biss.common.trade.Board"></a>

### Board
交易板块

| Name | Number | Description |
| ---- | ------ | ----------- |
| MAIN | 0 | 主板 |
| GEM | 1 | 创新板 |



<a name="biss.common.trade.Category"></a>

### Category
标的类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| COIN | 0 | 数字货币 |
| STOCK | 1 | 股票 |
| FUND | 2 | 基金 |



<a name="biss.common.trade.OrderFillStatus"></a>

### OrderFillStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| OFS_NONE | 0 |  |
| OFS_UNFILLED | 1 | 待成交 |
| OFS_PARTIAL_FILLED | 2 | 部分成交 |
| OFS_FULL_FILLED | 3 | 全部成交 |



<a name="biss.common.trade.OrderListType"></a>

### OrderListType


| Name | Number | Description |
| ---- | ------ | ----------- |
| OLT_CURRENT | 0 |  |
| OLT_HISTORY | 1 |  |
| OLT_24HOURS | 2 |  |
| OLT_DETAILS | 3 |  |



<a name="biss.common.trade.OrderStatus"></a>

### OrderStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| OS_NONE | 0 |  |
| OS_OPEN | 1 | 待成交 |
| OS_CLOSED | 2 | 全部成交 |
| OS_CANCELED | 3 | 已取消 |
| OS_EXPIRED | 4 | 已过期 |
| OS_INVALID | 5 | 废单 |



<a name="biss.common.trade.OrderType"></a>

### OrderType


| Name | Number | Description |
| ---- | ------ | ----------- |
| OT_NONE | 0 |  |
| OT_LIMIT | 1 | 限价单 |
| OT_MARKET | 2 | 市价单 |



<a name="biss.common.trade.SubCategory"></a>

### SubCategory
标的类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| SC_NONE | 0 |  |
| SC_US_STOCK | 1 | 美股 |
| SC_CRYPTO_ETF | 2 | 数字货币 ETF 基金 |



<a name="biss.common.trade.TickListType"></a>

### TickListType


| Name | Number | Description |
| ---- | ------ | ----------- |
| TLT_HISTORY | 0 |  |
| TLT_24HOURS | 1 |  |



<a name="biss.common.trade.TradeSide"></a>

### TradeSide


| Name | Number | Description |
| ---- | ------ | ----------- |
| TS_NONE | 0 |  |
| TS_BID | 1 | 买单 |
| TS_ASK | 2 | 卖单 |



<a name="biss.common.trade.TradeType"></a>

### TradeType


| Name | Number | Description |
| ---- | ------ | ----------- |
| TT_NONE | 0 |  |



<a name="biss.common.trade.TradingStatus"></a>

### TradingStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| TS_NORMAL | 0 | 正常交易 |
| TS_BREAK | 1 | 休市 |
| TS_SUSPENDED | 2 | 暂停交易 |
| TS_VOL_CTR | 3 | 波动中断(Volatility Control) |


 

 

 



## Scalar Value Types

| .proto Type | Notes | C++ Type | Java Type | Python Type |
| ----------- | ----- | -------- | --------- | ----------- |
| <a name="double" /> double |  | double | double | float |
| <a name="float" /> float |  | float | float | float |
| <a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int |
| <a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long |
| <a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long |
| <a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long |
| <a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int |
| <a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long |
| <a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int |
| <a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long |
| <a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int |
| <a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long |
| <a name="bool" /> bool |  | bool | boolean | boolean |
| <a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode |
| <a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str |


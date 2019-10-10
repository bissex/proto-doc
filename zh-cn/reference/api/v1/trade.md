# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/trade.proto](#proto/api/v1/trade.proto)
    - [AffordabilityReq](#biss.api.v1.trade.AffordabilityReq)
    - [AffordabilityResp](#biss.api.v1.trade.AffordabilityResp)
    - [BatchCancelReq](#biss.api.v1.trade.BatchCancelReq)
    - [BatchEntrustInfoReq](#biss.api.v1.trade.BatchEntrustInfoReq)
    - [BatchEntrustInfoResp](#biss.api.v1.trade.BatchEntrustInfoResp)
    - [BatchEntrustReq](#biss.api.v1.trade.BatchEntrustReq)
    - [BatchEntrustResp](#biss.api.v1.trade.BatchEntrustResp)
    - [CancelAllReq](#biss.api.v1.trade.CancelAllReq)
    - [CancelReq](#biss.api.v1.trade.CancelReq)
    - [EntrustInfoReq](#biss.api.v1.trade.EntrustInfoReq)
    - [EntrustInfoResp](#biss.api.v1.trade.EntrustInfoResp)
    - [EntrustReq](#biss.api.v1.trade.EntrustReq)
    - [EntrustResp](#biss.api.v1.trade.EntrustResp)
    - [Order](#biss.api.v1.trade.Order)
    - [OrderListReq](#biss.api.v1.trade.OrderListReq)
    - [OrderListResp](#biss.api.v1.trade.OrderListResp)
    - [PositionBriefResp](#biss.api.v1.trade.PositionBriefResp)
    - [PositionListReq](#biss.api.v1.trade.PositionListReq)
    - [PositionListResp](#biss.api.v1.trade.PositionListResp)
    - [PositionListResp.Position](#biss.api.v1.trade.PositionListResp.Position)
    - [Tick](#biss.api.v1.trade.Tick)
    - [TickerInfo](#biss.api.v1.trade.TickerInfo)
    - [TickerInfoResp](#biss.api.v1.trade.TickerInfoResp)
    - [TradeFee](#biss.api.v1.trade.TradeFee)
    - [VCMInfo](#biss.api.v1.trade.VCMInfo)
    - [VCMStatus](#biss.api.v1.trade.VCMStatus)
  
    - [OrderListSortType](#biss.api.v1.trade.OrderListSortType)
    - [PositionListSortType](#biss.api.v1.trade.PositionListSortType)
  
  
    - [Trade](#biss.api.v1.trade.Trade)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/trade.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/trade.proto



<a name="biss.api.v1.trade.AffordabilityReq"></a>

### AffordabilityReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  |  |
| type | [biss.common.trade.OrderType](#biss.common.trade.OrderType) |  | 订单类型 |
| price | [string](#string) |  | 尝试的交易价格 |
| qty | [string](#string) |  | 尝试交易数量 |






<a name="biss.api.v1.trade.AffordabilityResp"></a>

### AffordabilityResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| asset | [string](#string) |  | 用户资产 |
| afford_qty | [string](#string) |  |  |
| total | [string](#string) |  |  |
| fee | [string](#string) |  | 手续费 |
| fee_ratio | [string](#string) |  |  |
| usdt2usd | [string](#string) |  |  |






<a name="biss.api.v1.trade.BatchCancelReq"></a>

### BatchCancelReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| reqs | [CancelReq](#biss.api.v1.trade.CancelReq) | repeated |  |






<a name="biss.api.v1.trade.BatchEntrustInfoReq"></a>

### BatchEntrustInfoReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| oids | [uint64](#uint64) | repeated |  |






<a name="biss.api.v1.trade.BatchEntrustInfoResp"></a>

### BatchEntrustInfoResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| order_infos | [Order](#biss.api.v1.trade.Order) | repeated | order 信息 |






<a name="biss.api.v1.trade.BatchEntrustReq"></a>

### BatchEntrustReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| reqs | [EntrustReq](#biss.api.v1.trade.EntrustReq) | repeated | 批量委托请求数组 |






<a name="biss.api.v1.trade.BatchEntrustResp"></a>

### BatchEntrustResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| resps | [EntrustResp](#biss.api.v1.trade.EntrustResp) | repeated | 批量委托应答数组，长度、顺序与 BatchEntrustReq.reqs 一致 |






<a name="biss.api.v1.trade.CancelAllReq"></a>

### CancelAllReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 可有可无，有值就是撤销当前用户的该ticker的所有可撤委托 |






<a name="biss.api.v1.trade.CancelReq"></a>

### CancelReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| oid | [uint64](#uint64) |  |  |






<a name="biss.api.v1.trade.EntrustInfoReq"></a>

### EntrustInfoReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| oid | [uint64](#uint64) |  | order id |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |






<a name="biss.api.v1.trade.EntrustInfoResp"></a>

### EntrustInfoResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| order_info | [Order](#biss.api.v1.trade.Order) |  | order 信息 |






<a name="biss.api.v1.trade.EntrustReq"></a>

### EntrustReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| type | [biss.common.trade.OrderType](#biss.common.trade.OrderType) |  |  |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  |  |
| price | [string](#string) |  |  |
| qty | [string](#string) |  |  |






<a name="biss.api.v1.trade.EntrustResp"></a>

### EntrustResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| oid | [uint64](#uint64) |  | 订单编号 |
| code | [uint64](#uint64) |  | 错误码，批量委托使用 |
| failed | [bool](#bool) |  | 委托失败 |






<a name="biss.api.v1.trade.Order"></a>

### Order



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint64](#uint64) |  |  |
| type | [biss.common.trade.OrderType](#biss.common.trade.OrderType) |  | 订单类型 |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  | 交易方向 |
| price | [string](#string) |  | 价格 |
| qty | [string](#string) |  | 委托数量 |
| amount | [string](#string) |  | 交易额 |
| status | [biss.common.trade.OrderStatus](#biss.common.trade.OrderStatus) |  | 订单状态 |
| filled | [string](#string) |  | 已成交 |
| left | [string](#string) |  | 未成交 |
| time | [uint64](#uint64) |  | 委托时间 |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 交易对 |
| filled_avg | [string](#string) |  | 成交均价 |
| fee | [string](#string) |  | 手续费 |
| filledAmount | [string](#string) |  | 成交金额 |
| fillStatus | [biss.common.trade.OrderFillStatus](#biss.common.trade.OrderFillStatus) |  | 成交状态 |
| fill_ratio | [string](#string) |  |  |
| fees | [TradeFee](#biss.api.v1.trade.TradeFee) | repeated | 手续费明细 |






<a name="biss.api.v1.trade.OrderListReq"></a>

### OrderListReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  |  |
| sort_type | [OrderListSortType](#biss.api.v1.trade.OrderListSortType) |  |  |
| order_list_type | [biss.common.trade.OrderListType](#biss.common.trade.OrderListType) |  |  |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |






<a name="biss.api.v1.trade.OrderListResp"></a>

### OrderListResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  |  |
| sort_type | [OrderListSortType](#biss.api.v1.trade.OrderListSortType) |  |  |
| orders | [Order](#biss.api.v1.trade.Order) | repeated |  |






<a name="biss.api.v1.trade.PositionBriefResp"></a>

### PositionBriefResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| profit | [string](#string) |  | 盈亏 |
| ratio | [uint32](#uint32) |  | 盈亏比例 |
| hoding_amount | [string](#string) |  | 持仓市值 |
| current_amount | [string](#string) |  | 市值 |
| price_decimal | [uint32](#uint32) |  | 价格单位 |






<a name="biss.api.v1.trade.PositionListReq"></a>

### PositionListReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  |  |
| sort_type | [PositionListSortType](#biss.api.v1.trade.PositionListSortType) |  |  |






<a name="biss.api.v1.trade.PositionListResp"></a>

### PositionListResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  |  |
| sort_type | [PositionListSortType](#biss.api.v1.trade.PositionListSortType) |  |  |
| positions | [PositionListResp.Position](#biss.api.v1.trade.PositionListResp.Position) | repeated |  |






<a name="biss.api.v1.trade.PositionListResp.Position"></a>

### PositionListResp.Position



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| hoding_price | [string](#string) |  | 持仓成本 |
| current_price | [string](#string) |  | 现价 |
| qty | [string](#string) |  | 数量 |
| hoding_amount | [string](#string) |  | 持仓市值 |
| current_amount | [string](#string) |  | 市值 |
| profit | [string](#string) |  | 盈亏 |
| ratio | [int32](#int32) |  | 盈亏比例 |






<a name="biss.api.v1.trade.Tick"></a>

### Tick



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint64](#uint64) |  |  |
| type | [biss.common.trade.OrderType](#biss.common.trade.OrderType) |  | 订单类型 |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  | 交易方向 |
| price | [string](#string) |  | 价格 |
| qty | [string](#string) |  | 数量 |
| amount | [string](#string) |  | 市值 |
| fee | [string](#string) |  | 交易手续费 |
| time | [uint64](#uint64) |  | 成交时间 |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 交易对 |






<a name="biss.api.v1.trade.TickerInfo"></a>

### TickerInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| share_uint | [string](#string) |  | 交易单位，默认为 1 |
| min_bid_qty | [string](#string) |  | 最小买入数量 |
| max_bid_qty | [string](#string) |  | 最大买入数量 |
| min_ask_qty | [string](#string) |  | 最小卖出数量 |
| max_ask_qty | [string](#string) |  | 最大卖出数量 |
| trading_status | [biss.common.trade.TradingStatus](#biss.common.trade.TradingStatus) |  |  |
| vcm_info | [VCMInfo](#biss.api.v1.trade.VCMInfo) |  | 波动中断信息 |






<a name="biss.api.v1.trade.TickerInfoResp"></a>

### TickerInfoResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| info | [TickerInfo](#biss.api.v1.trade.TickerInfo) |  |  |






<a name="biss.api.v1.trade.TradeFee"></a>

### TradeFee



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 扣费币种 |
| qty | [string](#string) |  | 实扣数量 |
| original_qty | [string](#string) |  | 应扣数量 |
| discount_rate | [uint32](#uint32) |  | 平均折扣率，qty/original_qty*100 |






<a name="biss.api.v1.trade.VCMInfo"></a>

### VCMInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| upper_price_limit | [string](#string) |  | 触发上限 |
| lower_price_limit | [string](#string) |  | 触发下限 |
| cooling_off_period | [uint64](#uint64) |  | 冷却时间 |
| status | [VCMStatus](#biss.api.v1.trade.VCMStatus) |  | 当前状态 |






<a name="biss.api.v1.trade.VCMStatus"></a>

### VCMStatus
Volatility Control Mechanism Infomation


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| trigger_time | [uint64](#uint64) |  | 触发时间 |
| post_time | [uint64](#uint64) |  | 过期时间 |





 


<a name="biss.api.v1.trade.OrderListSortType"></a>

### OrderListSortType


| Name | Number | Description |
| ---- | ------ | ----------- |
| TIME | 0 | 委托时间 |
| STATUS | 1 | 订单状态 |
| ORDER_TYPE | 2 | 订单类型 |
| TRADE_SIDE | 3 | 交易方向 |
| ENTRUST_PRICE | 4 | 当前委托按照价格 |
| ENTRUST_QTY | 5 | 委托数量 |
| ENTRUST_AMOUNT | 6 | 委托总额 |
| FILLED_QTY | 7 | 成交数量 |
| FILLED_AMOUNT | 8 | 成交总额 |
| FILL_STATUS | 9 | 成交状态 |



<a name="biss.api.v1.trade.PositionListSortType"></a>

### PositionListSortType


| Name | Number | Description |
| ---- | ------ | ----------- |
| DEFAULT | 0 |  |
| HODING_PRICE | 1 |  |
| CURRENT_PRICE | 2 |  |
| QTY | 3 |  |
| HODING_AMOUNT | 4 |  |
| CURRENT_AMOUNT | 5 |  |
| PROFIT | 6 |  |
| RATIO | 7 |  |


 

 


<a name="biss.api.v1.trade.Trade"></a>

### Trade


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| TickerInfo | [.biss.common.trade.Ticker](#biss.common.trade.Ticker) | [TickerInfoResp](#biss.api.v1.trade.TickerInfoResp) | 获取标的信息 |
| Affordability | [AffordabilityReq](#biss.api.v1.trade.AffordabilityReq) | [AffordabilityResp](#biss.api.v1.trade.AffordabilityResp) | 可买可卖查询 |
| Entrust | [EntrustReq](#biss.api.v1.trade.EntrustReq) | [EntrustResp](#biss.api.v1.trade.EntrustResp) | 委托下单 |
| BatchEntrust | [BatchEntrustReq](#biss.api.v1.trade.BatchEntrustReq) | [BatchEntrustResp](#biss.api.v1.trade.BatchEntrustResp) | 批量委托下单 |
| Cancel | [CancelReq](#biss.api.v1.trade.CancelReq) | [.biss.common.Empty](#biss.common.Empty) | 取消订单 |
| BatchCancel | [BatchCancelReq](#biss.api.v1.trade.BatchCancelReq) | [.biss.common.Empty](#biss.common.Empty) | 批量取消订单 |
| CancelAll | [CancelAllReq](#biss.api.v1.trade.CancelAllReq) | [.biss.common.Empty](#biss.common.Empty) | 全部取消订单 |
| EntrustInfo | [EntrustInfoReq](#biss.api.v1.trade.EntrustInfoReq) | [EntrustInfoResp](#biss.api.v1.trade.EntrustInfoResp) | 委托信息(获取单个order信息) |
| BatchEntrustInfo | [BatchEntrustInfoReq](#biss.api.v1.trade.BatchEntrustInfoReq) | [BatchEntrustInfoResp](#biss.api.v1.trade.BatchEntrustInfoResp) | 委托信息(获取多个order信息) |
| EntrustList | [OrderListReq](#biss.api.v1.trade.OrderListReq) | [OrderListResp](#biss.api.v1.trade.OrderListResp) | 委托列表 |
| OrderHistoryList | [OrderListReq](#biss.api.v1.trade.OrderListReq) | [OrderListResp](#biss.api.v1.trade.OrderListResp) | 历史订单记录 |
| PositionList | [PositionListReq](#biss.api.v1.trade.PositionListReq) | [PositionListResp](#biss.api.v1.trade.PositionListResp) | 持仓列表 |
| PositionBrief | [.biss.common.Empty](#biss.common.Empty) | [PositionBriefResp](#biss.api.v1.trade.PositionBriefResp) stream | 持仓状态 |

 



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


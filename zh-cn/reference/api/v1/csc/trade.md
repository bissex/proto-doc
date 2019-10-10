# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/csc/trade.proto](#proto/api/v1/csc/trade.proto)
    - [AffordabilityReq](#biss.api.v1.csc.trade.AffordabilityReq)
    - [AffordabilityResp](#biss.api.v1.csc.trade.AffordabilityResp)
    - [BatchCancelReq](#biss.api.v1.csc.trade.BatchCancelReq)
    - [BatchEntrustInfoReq](#biss.api.v1.csc.trade.BatchEntrustInfoReq)
    - [BatchEntrustInfoResp](#biss.api.v1.csc.trade.BatchEntrustInfoResp)
    - [CancelAllReq](#biss.api.v1.csc.trade.CancelAllReq)
    - [CancelReq](#biss.api.v1.csc.trade.CancelReq)
    - [EntrustInfoReq](#biss.api.v1.csc.trade.EntrustInfoReq)
    - [EntrustInfoResp](#biss.api.v1.csc.trade.EntrustInfoResp)
    - [EntrustReq](#biss.api.v1.csc.trade.EntrustReq)
    - [EntrustResp](#biss.api.v1.csc.trade.EntrustResp)
    - [Order](#biss.api.v1.csc.trade.Order)
    - [OrderIndex](#biss.api.v1.csc.trade.OrderIndex)
    - [OrderListReq](#biss.api.v1.csc.trade.OrderListReq)
    - [OrderListResp](#biss.api.v1.csc.trade.OrderListResp)
    - [Tick](#biss.api.v1.csc.trade.Tick)
  
    - [OrderListSortType](#biss.api.v1.csc.trade.OrderListSortType)
  
  
    - [Trade](#biss.api.v1.csc.trade.Trade)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/csc/trade.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/csc/trade.proto



<a name="biss.api.v1.csc.trade.AffordabilityReq"></a>

### AffordabilityReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  |  |
| type | [biss.common.trade.OrderType](#biss.common.trade.OrderType) |  | 订单类型 |
| price_usd | [string](#string) |  | 尝试的交易价格(USD) |
| qty | [string](#string) |  | 尝试交易数量 |






<a name="biss.api.v1.csc.trade.AffordabilityResp"></a>

### AffordabilityResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| asset | [string](#string) |  | 用户资产 |
| afford_qty | [string](#string) |  |  |
| total | [string](#string) |  |  |
| fee | [string](#string) |  | 手续费(USDT) |
| fee_ratio | [string](#string) |  |  |
| usdt2usd | [string](#string) |  |  |






<a name="biss.api.v1.csc.trade.BatchCancelReq"></a>

### BatchCancelReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| order_indexs | [OrderIndex](#biss.api.v1.csc.trade.OrderIndex) | repeated |  |






<a name="biss.api.v1.csc.trade.BatchEntrustInfoReq"></a>

### BatchEntrustInfoReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| oids | [uint64](#uint64) | repeated |  |






<a name="biss.api.v1.csc.trade.BatchEntrustInfoResp"></a>

### BatchEntrustInfoResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| order_infos | [Order](#biss.api.v1.csc.trade.Order) | repeated | order 信息 |






<a name="biss.api.v1.csc.trade.CancelAllReq"></a>

### CancelAllReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 可有可无，有值就是撤销当前用户的该ticker的所有可撤委托 |






<a name="biss.api.v1.csc.trade.CancelReq"></a>

### CancelReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| oid | [uint64](#uint64) |  |  |






<a name="biss.api.v1.csc.trade.EntrustInfoReq"></a>

### EntrustInfoReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| oid | [uint64](#uint64) |  | order id |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |






<a name="biss.api.v1.csc.trade.EntrustInfoResp"></a>

### EntrustInfoResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| order_info | [Order](#biss.api.v1.csc.trade.Order) |  | order 信息 |






<a name="biss.api.v1.csc.trade.EntrustReq"></a>

### EntrustReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| type | [biss.common.trade.OrderType](#biss.common.trade.OrderType) |  |  |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  |  |
| price_usd | [string](#string) |  | 下单价格(USD) |
| qty | [string](#string) |  |  |






<a name="biss.api.v1.csc.trade.EntrustResp"></a>

### EntrustResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| oid | [uint64](#uint64) |  |  |






<a name="biss.api.v1.csc.trade.Order"></a>

### Order



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| oid | [uint64](#uint64) |  |  |
| type | [biss.common.trade.OrderType](#biss.common.trade.OrderType) |  | 订单类型 |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  | 交易方向 |
| price | [string](#string) |  | 价格(USDT) |
| qty | [string](#string) |  | 委托数量 |
| amount | [string](#string) |  | 交易额(USDT) |
| status | [biss.common.trade.OrderStatus](#biss.common.trade.OrderStatus) |  | 订单状态 |
| filled | [string](#string) |  | 已成交 |
| left | [string](#string) |  | 未成交 |
| time | [uint64](#uint64) |  | 委托时间 |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 交易对 |
| filled_avg | [string](#string) |  | 成交均价(USDT) |
| fee | [string](#string) |  | 手续费(USDT) |
| filledAmount | [string](#string) |  | 成交金额(USDT) |
| fillStatus | [biss.common.trade.OrderFillStatus](#biss.common.trade.OrderFillStatus) |  | 成交状态 |
| fill_ratio | [string](#string) |  |  |






<a name="biss.api.v1.csc.trade.OrderIndex"></a>

### OrderIndex



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| oid | [uint64](#uint64) |  |  |






<a name="biss.api.v1.csc.trade.OrderListReq"></a>

### OrderListReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  |  |
| sort_type | [OrderListSortType](#biss.api.v1.csc.trade.OrderListSortType) |  |  |
| order_list_type | [biss.common.trade.OrderListType](#biss.common.trade.OrderListType) |  |  |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |






<a name="biss.api.v1.csc.trade.OrderListResp"></a>

### OrderListResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  |  |
| sort_type | [OrderListSortType](#biss.api.v1.csc.trade.OrderListSortType) |  |  |
| orders | [Order](#biss.api.v1.csc.trade.Order) | repeated |  |






<a name="biss.api.v1.csc.trade.Tick"></a>

### Tick



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint64](#uint64) |  |  |
| type | [biss.common.trade.OrderType](#biss.common.trade.OrderType) |  | 订单类型 |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  | 交易方向 |
| price | [string](#string) |  | 价格(USDT) |
| qty | [string](#string) |  | 数量 |
| amount | [string](#string) |  | 市值(USDT) |
| fee | [string](#string) |  | 交易手续费(USDT) |
| time | [uint64](#uint64) |  | 成交时间 |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 交易对 |





 


<a name="biss.api.v1.csc.trade.OrderListSortType"></a>

### OrderListSortType


| Name | Number | Description |
| ---- | ------ | ----------- |
| TIME | 0 |  |
| STATUS | 1 |  |


 

 


<a name="biss.api.v1.csc.trade.Trade"></a>

### Trade


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Affordability | [AffordabilityReq](#biss.api.v1.csc.trade.AffordabilityReq) | [AffordabilityResp](#biss.api.v1.csc.trade.AffordabilityResp) | 可买可卖查询 |
| Entrust | [EntrustReq](#biss.api.v1.csc.trade.EntrustReq) | [EntrustResp](#biss.api.v1.csc.trade.EntrustResp) | 委托下单 |
| Cancel | [CancelReq](#biss.api.v1.csc.trade.CancelReq) | [.biss.common.Empty](#biss.common.Empty) | 取消订单 |
| BatchCancel | [BatchCancelReq](#biss.api.v1.csc.trade.BatchCancelReq) | [.biss.common.Empty](#biss.common.Empty) | 批量取消订单 |
| CancelAll | [CancelAllReq](#biss.api.v1.csc.trade.CancelAllReq) | [.biss.common.Empty](#biss.common.Empty) | 全部取消订单 |
| EntrustInfo | [EntrustInfoReq](#biss.api.v1.csc.trade.EntrustInfoReq) | [EntrustInfoResp](#biss.api.v1.csc.trade.EntrustInfoResp) | 委托信息(获取单个order信息) |
| BatchEntrustInfo | [BatchEntrustInfoReq](#biss.api.v1.csc.trade.BatchEntrustInfoReq) | [BatchEntrustInfoResp](#biss.api.v1.csc.trade.BatchEntrustInfoResp) | 委托信息(获取多个order信息) |
| EntrustList | [OrderListReq](#biss.api.v1.csc.trade.OrderListReq) | [OrderListResp](#biss.api.v1.csc.trade.OrderListResp) | 委托列表 |

 



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


# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/activity/bissup/exchange.proto](#proto/api/v1/activity/bissup/exchange.proto)
    - [ExGlobalStatus](#biss.api.v1.activity.bissup.ExGlobalStatus)
    - [ExInfo](#biss.api.v1.activity.bissup.ExInfo)
    - [ExLimit](#biss.api.v1.activity.bissup.ExLimit)
    - [ExchangeReq](#biss.api.v1.activity.bissup.ExchangeReq)
  
  
  
    - [ExchangeSvc](#biss.api.v1.activity.bissup.ExchangeSvc)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/activity/bissup/exchange.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/activity/bissup/exchange.proto



<a name="biss.api.v1.activity.bissup.ExGlobalStatus"></a>

### ExGlobalStatus
兑换全局信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| amount_total | [string](#string) |  | 兑换总额(market) |
| qty_total | [string](#string) |  | 兑换总量(symbol) |






<a name="biss.api.v1.activity.bissup.ExInfo"></a>

### ExInfo
个人兑换信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| done | [bool](#bool) |  | 完成兑换 |
| amount_exchange | [string](#string) |  | 兑换额(market) |
| amount_settlement | [string](#string) |  | 清算额(market) |
| qty_exchange | [string](#string) |  | 兑换量(symbol) |
| qty_settlement | [string](#string) |  | 清算量(symbol) |
| time | [uint64](#uint64) |  | 时间(UTC timestamp in millisecond) |






<a name="biss.api.v1.activity.bissup.ExLimit"></a>

### ExLimit
个人兑换限制


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rate | [string](#string) |  | 兑换率(1 market = ? symbol) |
| amount_limit | [string](#string) |  | 额限制(market) |
| qty_limit | [string](#string) |  | 量限制(symbol) |






<a name="biss.api.v1.activity.bissup.ExchangeReq"></a>

### ExchangeReq
兑换请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 交易对 |
| amount | [string](#string) |  | 兑换额(market) |





 

 

 


<a name="biss.api.v1.activity.bissup.ExchangeSvc"></a>

### ExchangeSvc


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetExGlobalStatus | [.biss.common.trade.Ticker](#biss.common.trade.Ticker) | [ExGlobalStatus](#biss.api.v1.activity.bissup.ExGlobalStatus) | 获取兑换全局信息 |
| GetExLimit | [.biss.common.trade.Ticker](#biss.common.trade.Ticker) | [ExLimit](#biss.api.v1.activity.bissup.ExLimit) | 获取个人兑换限制 |
| Exchange | [ExchangeReq](#biss.api.v1.activity.bissup.ExchangeReq) | [.biss.common.Empty](#biss.common.Empty) | 兑换 |
| GetExInfo | [.biss.common.trade.Ticker](#biss.common.trade.Ticker) | [ExInfo](#biss.api.v1.activity.bissup.ExInfo) | 获取个人兑换信息 |

 



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


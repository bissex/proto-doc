# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/activity/ieo/ieo.proto](#proto/api/v1/activity/ieo/ieo.proto)
    - [AvailablLimit](#biss.api.v1.activity.ieo.ieo.AvailablLimit)
    - [IEOStatus](#biss.api.v1.activity.ieo.ieo.IEOStatus)
    - [PublicTradingInfo](#biss.api.v1.activity.ieo.ieo.PublicTradingInfo)
    - [SecKillInfo](#biss.api.v1.activity.ieo.ieo.SecKillInfo)
  
  
  
    - [Ieo](#biss.api.v1.activity.ieo.ieo.Ieo)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/activity/ieo/ieo.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/activity/ieo/ieo.proto



<a name="biss.api.v1.activity.ieo.ieo.AvailablLimit"></a>

### AvailablLimit
可用额度


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| uid | [uint64](#uint64) |  | 用户ID |
| availabl_limit | [string](#string) |  | 可用额度 |






<a name="biss.api.v1.activity.ieo.ieo.IEOStatus"></a>

### IEOStatus
全局状态


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| cur_time | [uint64](#uint64) |  | 当前时间, UTC timestamp in millisecond |
| sec_kill_info | [SecKillInfo](#biss.api.v1.activity.ieo.ieo.SecKillInfo) |  |  |
| public_trading_info | [PublicTradingInfo](#biss.api.v1.activity.ieo.ieo.PublicTradingInfo) |  |  |






<a name="biss.api.v1.activity.ieo.ieo.PublicTradingInfo"></a>

### PublicTradingInfo
公开交易状态


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| on | [bool](#bool) |  | 是否已经开始公开交易 |
| start_time | [uint64](#uint64) |  | 公开交易时间, UTC timestamp in millisecond |
| countdown | [uint64](#uint64) |  | 倒计时, millisecond |






<a name="biss.api.v1.activity.ieo.ieo.SecKillInfo"></a>

### SecKillInfo
秒杀状态


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| on | [bool](#bool) |  | 是否秒杀中 |
| next_round_no | [uint32](#uint32) |  | 下轮秒杀轮次, 0 表示全部秒杀已结束 |
| next_round_start_time | [uint64](#uint64) |  | 下轮秒杀开始时间, UTC timestamp in millisecond |
| next_round_finish_time | [uint64](#uint64) |  | 下轮秒杀结束时间, UTC timestamp in millisecond |
| next_round_countdown | [uint64](#uint64) |  | 下轮秒杀倒计时, next_round_start_time - cur_time, millisecond |





 

 

 


<a name="biss.api.v1.activity.ieo.ieo.Ieo"></a>

### Ieo


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetIEOStatus | [.biss.common.trade.Ticker](#biss.common.trade.Ticker) | [IEOStatus](#biss.api.v1.activity.ieo.ieo.IEOStatus) | 获取全局状态 |
| GetAvailablLimit | [.biss.common.trade.Ticker](#biss.common.trade.Ticker) | [AvailablLimit](#biss.api.v1.activity.ieo.ieo.AvailablLimit) | 获取可用额度 |
| IeoAffordability | [.biss.api.v1.trade.AffordabilityReq](#biss.api.v1.trade.AffordabilityReq) | [.biss.api.v1.trade.AffordabilityResp](#biss.api.v1.trade.AffordabilityResp) | IEO 可买可卖查询 |
| IeoEntrust | [.biss.api.v1.trade.EntrustReq](#biss.api.v1.trade.EntrustReq) | [.biss.api.v1.trade.EntrustResp](#biss.api.v1.trade.EntrustResp) | IEO 委托下单 |

 



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


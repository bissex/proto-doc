# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/push.proto](#proto/api/v1/push.proto)
    - [Hertbeat](#biss.api.v1.push.Hertbeat)
    - [KLineReq](#biss.api.v1.push.KLineReq)
    - [OpenAsyncReq](#biss.api.v1.push.OpenAsyncReq)
    - [PositionReq](#biss.api.v1.push.PositionReq)
    - [Pub](#biss.api.v1.push.Pub)
    - [PushMessage](#biss.api.v1.push.PushMessage)
    - [RealTimeReq](#biss.api.v1.push.RealTimeReq)
    - [Sub](#biss.api.v1.push.Sub)
    - [SubTickReq](#biss.api.v1.push.SubTickReq)
  
  
  
    - [PushChannel](#biss.api.v1.push.PushChannel)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/push.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/push.proto



<a name="biss.api.v1.push.Hertbeat"></a>

### Hertbeat







<a name="biss.api.v1.push.KLineReq"></a>

### KLineReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sub_uuid | [string](#string) |  |  |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| peroid | [biss.api.v1.quote.KLinePeroid](#biss.api.v1.quote.KLinePeroid) |  |  |






<a name="biss.api.v1.push.OpenAsyncReq"></a>

### OpenAsyncReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sub_uuid | [string](#string) |  |  |






<a name="biss.api.v1.push.PositionReq"></a>

### PositionReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sub_uuid | [string](#string) |  |  |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| precision | [string](#string) |  | 盘口合并深度 |






<a name="biss.api.v1.push.Pub"></a>

### Pub



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| mesg | [google.protobuf.Any](#google.protobuf.Any) |  |  |






<a name="biss.api.v1.push.PushMessage"></a>

### PushMessage



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| realtime | [biss.api.v1.quote.RealTimeUpdate](#biss.api.v1.quote.RealTimeUpdate) |  |  |
| tick | [biss.api.v1.quote.TickUpdate](#biss.api.v1.quote.TickUpdate) |  |  |
| kline | [biss.api.v1.quote.KLineUpdate](#biss.api.v1.quote.KLineUpdate) |  |  |
| position | [biss.api.v1.quote.PositionUpdate](#biss.api.v1.quote.PositionUpdate) |  |  |
| hb | [Hertbeat](#biss.api.v1.push.Hertbeat) |  |  |






<a name="biss.api.v1.push.RealTimeReq"></a>

### RealTimeReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sub_uuid | [string](#string) |  |  |
| tickers | [biss.common.trade.Ticker](#biss.common.trade.Ticker) | repeated | 请求的ticker列表，包含请求单个ticker |






<a name="biss.api.v1.push.Sub"></a>

### Sub



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| topic | [string](#string) |  |  |






<a name="biss.api.v1.push.SubTickReq"></a>

### SubTickReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sub_uuid | [string](#string) |  |  |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| last | [uint32](#uint32) |  | 最新历史 Tick 数量 |





 

 

 


<a name="biss.api.v1.push.PushChannel"></a>

### PushChannel


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| OpenAsync | [OpenAsyncReq](#biss.api.v1.push.OpenAsyncReq) | [PushMessage](#biss.api.v1.push.PushMessage) stream |  |
| Open | [Sub](#biss.api.v1.push.Sub) stream | [Pub](#biss.api.v1.push.Pub) stream |  |
| SubRealTime | [RealTimeReq](#biss.api.v1.push.RealTimeReq) | [.biss.common.Empty](#biss.common.Empty) | ============= 订阅行情 订阅实时行情 |
| UnsubRealTime | [RealTimeReq](#biss.api.v1.push.RealTimeReq) | [.biss.common.Empty](#biss.common.Empty) |  |
| SubTick | [SubTickReq](#biss.api.v1.push.SubTickReq) | [.biss.common.Empty](#biss.common.Empty) | 逐笔行情 |
| UnsubTick | [SubTickReq](#biss.api.v1.push.SubTickReq) | [.biss.common.Empty](#biss.common.Empty) |  |
| SubKLine | [KLineReq](#biss.api.v1.push.KLineReq) | [.biss.common.Empty](#biss.common.Empty) | 订阅 K 线行情 |
| UnsubKLine | [KLineReq](#biss.api.v1.push.KLineReq) | [.biss.common.Empty](#biss.common.Empty) |  |
| SubPosition | [PositionReq](#biss.api.v1.push.PositionReq) | [.biss.common.Empty](#biss.common.Empty) | 订阅盘口 |
| UnsubPosition | [PositionReq](#biss.api.v1.push.PositionReq) | [.biss.common.Empty](#biss.common.Empty) |  |

 



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


# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/activity/bissup/bissup.proto](#proto/api/v1/activity/bissup/bissup.proto)
    - [BissupConfig](#biss.api.v1.activity.bissup.BissupConfig)
    - [BissupConfigList](#biss.api.v1.activity.bissup.BissupConfigList)
    - [RepurchaseRecord](#biss.api.v1.activity.bissup.RepurchaseRecord)
    - [RepurchaseRecordItem](#biss.api.v1.activity.bissup.RepurchaseRecordItem)
    - [RepurchaseReq](#biss.api.v1.activity.bissup.RepurchaseReq)
    - [SubscriptionInfo](#biss.api.v1.activity.bissup.SubscriptionInfo)
    - [SubscriptionList](#biss.api.v1.activity.bissup.SubscriptionList)
  
    - [BissupPhase](#biss.api.v1.activity.bissup.BissupPhase)
  
  
    - [BissupSvc](#biss.api.v1.activity.bissup.BissupSvc)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/activity/bissup/bissup.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/activity/bissup/bissup.proto



<a name="biss.api.v1.activity.bissup.BissupConfig"></a>

### BissupConfig
Bissup配置列表


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| phase | [BissupPhase](#biss.api.v1.activity.bissup.BissupPhase) |  | 基本配置

阶段 |
| start_time | [uint64](#uint64) |  | 开始&amp;结束时间(UTC timestamp in millisecond) |
| finish_time | [uint64](#uint64) |  | [start_time, finish_time) |
| round_no | [uint32](#uint32) |  | 附加配置

轮次(非0时有意义)BP_SUBSCRIPTION/BP_SUB_SETTLEMENT/BP_FREE_TRADING/BP_FT_SETTLEMENT |
| limit_price | [string](#string) |  | 限价价格(非空时有意义)BP_SUBSCRIPTION |






<a name="biss.api.v1.activity.bissup.BissupConfigList"></a>

### BissupConfigList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [BissupConfig](#biss.api.v1.activity.bissup.BissupConfig) | repeated |  |






<a name="biss.api.v1.activity.bissup.RepurchaseRecord"></a>

### RepurchaseRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [RepurchaseRecordItem](#biss.api.v1.activity.bissup.RepurchaseRecordItem) | repeated |  |






<a name="biss.api.v1.activity.bissup.RepurchaseRecordItem"></a>

### RepurchaseRecordItem
回购记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| round_no | [uint32](#uint32) |  | 轮次 |
| price | [string](#string) |  | 回购价格 |
| qty | [string](#string) |  | 回购数量 |
| amount | [string](#string) |  | 回购交易额 |
| time | [uint64](#uint64) |  | 时间(UTC timestamp in millisecond) |






<a name="biss.api.v1.activity.bissup.RepurchaseReq"></a>

### RepurchaseReq
回购请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 交易对 |
| round_no | [uint32](#uint32) |  | 轮次 |
| qty | [string](#string) |  | 回购数量 |






<a name="biss.api.v1.activity.bissup.SubscriptionInfo"></a>

### SubscriptionInfo
认购列表


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| round_no | [uint32](#uint32) |  | 轮次 |
| price_subscription | [string](#string) |  | 认购价格 |
| price_repurchase | [string](#string) |  | 回购价格 |
| qty_subscription | [string](#string) |  | 认购数量 |
| qty_repurchase | [string](#string) |  | 可回购数量 |
| amount | [string](#string) |  | 可回购交易额 |






<a name="biss.api.v1.activity.bissup.SubscriptionList"></a>

### SubscriptionList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [SubscriptionInfo](#biss.api.v1.activity.bissup.SubscriptionInfo) | repeated |  |





 


<a name="biss.api.v1.activity.bissup.BissupPhase"></a>

### BissupPhase
Bissup 阶段

| Name | Number | Description |
| ---- | ------ | ----------- |
| BP_NONE | 0 |  |
| BP_START | 1 | 开始 |
| BP_SUBSCRIPTION | 2 | 认购 |
| BP_SUB_SETTLEMENT | 3 | 认购清算 |
| BP_FREE_TRADING | 4 | 自由交易 |
| BP_FT_SETTLEMENT | 5 | 自由交易清算 |
| BP_PUBLIC_TRADING | 6 | 公开交易 |


 

 


<a name="biss.api.v1.activity.bissup.BissupSvc"></a>

### BissupSvc


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetBissupConfigList | [.biss.common.trade.Ticker](#biss.common.trade.Ticker) | [BissupConfigList](#biss.api.v1.activity.bissup.BissupConfigList) | 获取Bissup配置列表 |
| GetSubscriptionList | [.biss.common.trade.Ticker](#biss.common.trade.Ticker) | [SubscriptionList](#biss.api.v1.activity.bissup.SubscriptionList) | 获取认购列表 |
| Repurchase | [RepurchaseReq](#biss.api.v1.activity.bissup.RepurchaseReq) | [.biss.common.Empty](#biss.common.Empty) | 回购 |
| GetRepurchaseRecord | [.biss.common.trade.Ticker](#biss.common.trade.Ticker) | [RepurchaseRecord](#biss.api.v1.activity.bissup.RepurchaseRecord) | 获取回购记录 |

 



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


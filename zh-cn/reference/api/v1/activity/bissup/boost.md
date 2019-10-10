# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/activity/bissup/boost.proto](#proto/api/v1/activity/bissup/boost.proto)
    - [BoostInfo](#biss.api.v1.activity.bissup.BoostInfo)
    - [BoostInfoReq](#biss.api.v1.activity.bissup.BoostInfoReq)
    - [BoostReq](#biss.api.v1.activity.bissup.BoostReq)
    - [BoostResp](#biss.api.v1.activity.bissup.BoostResp)
  
    - [BoostEvent](#biss.api.v1.activity.bissup.BoostEvent)
  
  
    - [BoostSvc](#biss.api.v1.activity.bissup.BoostSvc)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/activity/bissup/boost.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/activity/bissup/boost.proto



<a name="biss.api.v1.activity.bissup.BoostInfo"></a>

### BoostInfo
助力信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| qualified | [bool](#bool) |  | 合格 |
| required_num | [uint32](#uint32) |  | 需要数量 |
| existing_num | [uint32](#uint32) |  | 已有数量 |
| remaining_num | [uint32](#uint32) |  | 剩余数量 |






<a name="biss.api.v1.activity.bissup.BoostInfoReq"></a>

### BoostInfoReq
助力信息请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| event | [BoostEvent](#biss.api.v1.activity.bissup.BoostEvent) |  | 活动 |






<a name="biss.api.v1.activity.bissup.BoostReq"></a>

### BoostReq
助力请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| event | [BoostEvent](#biss.api.v1.activity.bissup.BoostEvent) |  | 活动 |
| code | [string](#string) |  | 助力码 |






<a name="biss.api.v1.activity.bissup.BoostResp"></a>

### BoostResp
助力应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| seq_no | [uint32](#uint32) |  | 序号 |





 


<a name="biss.api.v1.activity.bissup.BoostEvent"></a>

### BoostEvent
助力活动

| Name | Number | Description |
| ---- | ------ | ----------- |
| BE_NONE | 0 |  |
| BE_ETF | 1 | ETF |


 

 


<a name="biss.api.v1.activity.bissup.BoostSvc"></a>

### BoostSvc


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetBoostInfo | [BoostInfoReq](#biss.api.v1.activity.bissup.BoostInfoReq) | [BoostInfo](#biss.api.v1.activity.bissup.BoostInfo) | 获取助力信息 |
| Boost | [BoostReq](#biss.api.v1.activity.bissup.BoostReq) | [BoostResp](#biss.api.v1.activity.bissup.BoostResp) | 助力 |

 



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


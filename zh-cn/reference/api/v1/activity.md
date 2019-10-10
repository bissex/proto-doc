# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/activity.proto](#proto/api/v1/activity.proto)
    - [BookCSCReq](#biss.api.v1.activity.BookCSCReq)
    - [BookCSCResp](#biss.api.v1.activity.BookCSCResp)
    - [CSCBookCountResp](#biss.api.v1.activity.CSCBookCountResp)
  
  
  
    - [Activity](#biss.api.v1.activity.Activity)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/activity.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/activity.proto



<a name="biss.api.v1.activity.BookCSCReq"></a>

### BookCSCReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| nation_code | [string](#string) |  | 国家码 |
| mobile | [string](#string) |  |  |
| source | [uint32](#uint32) |  | 标记用户参加活动的来源(1:公众号, 2: 个人微信，3: WEB端) |






<a name="biss.api.v1.activity.BookCSCResp"></a>

### BookCSCResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| book_code | [string](#string) |  | 在预约b股的请求里是预约码 |






<a name="biss.api.v1.activity.CSCBookCountResp"></a>

### CSCBookCountResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| book_count | [uint32](#uint32) |  | 参加预约人数 |





 

 

 


<a name="biss.api.v1.activity.Activity"></a>

### Activity


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| BookCSC | [BookCSCReq](#biss.api.v1.activity.BookCSCReq) | [BookCSCResp](#biss.api.v1.activity.BookCSCResp) | 美股预约活动 |
| GetCSCBookCount | [.biss.common.Empty](#biss.common.Empty) | [CSCBookCountResp](#biss.api.v1.activity.CSCBookCountResp) | 获取活动的参与人数 |

 



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


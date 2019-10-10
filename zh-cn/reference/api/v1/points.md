# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/points.proto](#proto/api/v1/points.proto)
    - [PointsInfo](#biss.api.v1.points.PointsInfo)
    - [PointsRatio](#biss.api.v1.points.PointsRatio)
    - [PointsRecord](#biss.api.v1.points.PointsRecord)
    - [PointsRecordItem](#biss.api.v1.points.PointsRecordItem)
    - [PointsRecordReq](#biss.api.v1.points.PointsRecordReq)
  
    - [PointsType](#biss.api.v1.points.PointsType)
  
  
    - [PointsSvc](#biss.api.v1.points.PointsSvc)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/points.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/points.proto



<a name="biss.api.v1.points.PointsInfo"></a>

### PointsInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| points | [uint64](#uint64) |  | 总积分 |
| points_today | [uint64](#uint64) |  | 今日积分 |
| ratio | [PointsRatio](#biss.api.v1.points.PointsRatio) | repeated | 积分比例 |






<a name="biss.api.v1.points.PointsRatio"></a>

### PointsRatio
积分信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [PointsType](#biss.api.v1.points.PointsType) |  | 类型 |
| points | [uint64](#uint64) |  | 积分 |
| percentage | [string](#string) |  | 百分比 |






<a name="biss.api.v1.points.PointsRecord"></a>

### PointsRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pagination | [biss.common.PaginationResp](#biss.common.PaginationResp) |  | 分页信息 |
| items | [PointsRecordItem](#biss.api.v1.points.PointsRecordItem) | repeated |  |






<a name="biss.api.v1.points.PointsRecordItem"></a>

### PointsRecordItem
积分记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 时间(UTC timestamp in millisecond) |
| type | [PointsType](#biss.api.v1.points.PointsType) |  | 类型 |
| description | [string](#string) |  | 说明 |
| points | [uint64](#uint64) |  | 积分 |






<a name="biss.api.v1.points.PointsRecordReq"></a>

### PointsRecordReq
积分记录请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pagination | [biss.common.PaginationReq](#biss.common.PaginationReq) |  | 分页信息 |





 


<a name="biss.api.v1.points.PointsType"></a>

### PointsType
积分类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| PT_NONE | 0 |  |
| PT_REFERRAL | 1 | 邀请积分 |
| PT_TRADING | 2 | 交易积分 |
| PT_POSITION | 3 | 持仓积分 |
| PT_OTHER | 4 | 其他积分 |


 

 


<a name="biss.api.v1.points.PointsSvc"></a>

### PointsSvc


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetPointsInfo | [.biss.common.Empty](#biss.common.Empty) | [PointsInfo](#biss.api.v1.points.PointsInfo) | 积分信息 |
| GetPointsRecord | [PointsRecordReq](#biss.api.v1.points.PointsRecordReq) | [PointsRecord](#biss.api.v1.points.PointsRecord) | 积分记录 |

 



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


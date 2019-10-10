# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/activity/bissup/community.proto](#proto/api/v1/activity/bissup/community.proto)
    - [CommunityGlobalStatus](#biss.api.v1.activity.bissup.CommunityGlobalStatus)
    - [CommunityInfo](#biss.api.v1.activity.bissup.CommunityInfo)
    - [CommunityList](#biss.api.v1.activity.bissup.CommunityList)
    - [LikeReq](#biss.api.v1.activity.bissup.LikeReq)
  
  
  
    - [CommunitySvc](#biss.api.v1.activity.bissup.CommunitySvc)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/activity/bissup/community.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/activity/bissup/community.proto



<a name="biss.api.v1.activity.bissup.CommunityGlobalStatus"></a>

### CommunityGlobalStatus
社区全局信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| start_time | [uint64](#uint64) |  | 开始&amp;结束时间(UTC timestamp in millisecond) |
| finish_time | [uint64](#uint64) |  | [start_time, finish_time) |
| threshold | [uint32](#uint32) |  | 点赞阈值 |
| reward_symbol | [string](#string) |  | 奖励标的 |
| reward_total | [string](#string) |  | 总奖励 |
| reward_divided | [string](#string) |  | 瓜分奖励 |
| liked | [bool](#bool) |  | 是否已赞 |
| can_like | [bool](#bool) |  | 是否可赞 |
| can_call | [bool](#bool) |  | 是否可打 Call |






<a name="biss.api.v1.activity.bissup.CommunityInfo"></a>

### CommunityInfo
社区列表


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint32](#uint32) |  | id |
| no | [uint32](#uint32) |  | 序号 |
| name | [string](#string) |  | 名称 |
| likes | [uint32](#uint32) |  | 点赞数 |
| progress_pct | [string](#string) |  | 进度百分比 |
| update_time | [uint64](#uint64) |  | 更新时间(UTC timestamp in millisecond) |
| liked | [bool](#bool) |  | 是否已赞 |






<a name="biss.api.v1.activity.bissup.CommunityList"></a>

### CommunityList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [CommunityInfo](#biss.api.v1.activity.bissup.CommunityInfo) | repeated |  |






<a name="biss.api.v1.activity.bissup.LikeReq"></a>

### LikeReq
点赞请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint32](#uint32) |  | id |





 

 

 


<a name="biss.api.v1.activity.bissup.CommunitySvc"></a>

### CommunitySvc


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetCommunityGlobalStatus | [.biss.common.Empty](#biss.common.Empty) | [CommunityGlobalStatus](#biss.api.v1.activity.bissup.CommunityGlobalStatus) | 获取社区全局信息 |
| GetCommunityList | [.biss.common.Empty](#biss.common.Empty) | [CommunityList](#biss.api.v1.activity.bissup.CommunityList) | 获取社区列表 |
| Like | [LikeReq](#biss.api.v1.activity.bissup.LikeReq) | [.biss.common.Empty](#biss.common.Empty) | 点赞 |

 



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


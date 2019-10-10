# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/election/reward.proto](#proto/api/v1/election/reward.proto)
    - [ElectedDailyReward](#biss.api.v1.election.ElectedDailyReward)
    - [NewlyElectedLBReward](#biss.api.v1.election.NewlyElectedLBReward)
    - [RewardRecord](#biss.api.v1.election.RewardRecord)
    - [RewardRecordItem](#biss.api.v1.election.RewardRecordItem)
    - [RewardRecordReq](#biss.api.v1.election.RewardRecordReq)
  
    - [LBRewardType](#biss.api.v1.election.LBRewardType)
    - [RewardType](#biss.api.v1.election.RewardType)
  
  
    - [RewardSvc](#biss.api.v1.election.RewardSvc)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/election/reward.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/election/reward.proto



<a name="biss.api.v1.election.ElectedDailyReward"></a>

### ElectedDailyReward
当选每日奖励


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| daily_time | [uint64](#uint64) |  | 每日时间(UTC timestamp in millisecond)(仅年月日有效) |
| reward | [string](#string) |  | 奖励 |






<a name="biss.api.v1.election.NewlyElectedLBReward"></a>

### NewlyElectedLBReward
新当选排行榜奖励


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| reward_time | [uint64](#uint64) |  | 奖励时间(UTC timestamp in millisecond) |
| votes | [string](#string) |  | 票数 |
| type | [LBRewardType](#biss.api.v1.election.LBRewardType) |  | 类型 |
| reward | [string](#string) |  | 奖励 |






<a name="biss.api.v1.election.RewardRecord"></a>

### RewardRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [RewardRecordItem](#biss.api.v1.election.RewardRecordItem) | repeated |  |






<a name="biss.api.v1.election.RewardRecordItem"></a>

### RewardRecordItem
奖励记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| e_daily | [ElectedDailyReward](#biss.api.v1.election.ElectedDailyReward) |  | 当选每日奖励 |
| new_e_lb | [NewlyElectedLBReward](#biss.api.v1.election.NewlyElectedLBReward) |  | 新当选排行榜奖励 |






<a name="biss.api.v1.election.RewardRecordReq"></a>

### RewardRecordReq
奖励记录请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| type | [RewardType](#biss.api.v1.election.RewardType) |  | 奖励类型 |





 


<a name="biss.api.v1.election.LBRewardType"></a>

### LBRewardType
排行榜奖励类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| LRT_NONE | 0 |  |
| LRT_DIV_FIRST | 1 | 瓜分第一名 |
| LRT_DIV_SECOND | 2 | 瓜分第二名 |
| LRT_DIV_THIRD | 3 | 瓜分第三名 |



<a name="biss.api.v1.election.RewardType"></a>

### RewardType
奖励类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| RT_VOTER_MIN | 0 | 投票者身份 |
| RT_VOTER_VOTE_DAILY | 1 | 投票每日奖励 |
| RT_VOTER_NEWLY_ELECTED_LB | 2 | 新当选排行榜奖励 |
| RT_VOTER_MAX | 3 |  |
| RT_CANDIDATE_MIN | 100 | 候选人身份 |
| RT_CANDIDATE_ELECTED_DAILY | 101 | 当选每日奖励 |
| RT_CANDIDATE_MAX | 102 |  |


 

 


<a name="biss.api.v1.election.RewardSvc"></a>

### RewardSvc


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetRewardRecord | [RewardRecordReq](#biss.api.v1.election.RewardRecordReq) | [RewardRecord](#biss.api.v1.election.RewardRecord) | 获取奖励记录 |

 



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


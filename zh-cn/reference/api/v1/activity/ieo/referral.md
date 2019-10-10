# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/activity/ieo/referral.proto](#proto/api/v1/activity/ieo/referral.proto)
    - [FomoAwardRecord](#biss.api.v1.activity.ieo.referral.FomoAwardRecord)
    - [FomoAwardRecordItem](#biss.api.v1.activity.ieo.referral.FomoAwardRecordItem)
    - [FomoRewardInfo](#biss.api.v1.activity.ieo.referral.FomoRewardInfo)
    - [GlobalStatus](#biss.api.v1.activity.ieo.referral.GlobalStatus)
    - [UserInfo](#biss.api.v1.activity.ieo.referral.UserInfo)
  
    - [FomoAwardType](#biss.api.v1.activity.ieo.referral.FomoAwardType)
  
  
    - [Referral](#biss.api.v1.activity.ieo.referral.Referral)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/activity/ieo/referral.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/activity/ieo/referral.proto



<a name="biss.api.v1.activity.ieo.referral.FomoAwardRecord"></a>

### FomoAwardRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [FomoAwardRecordItem](#biss.api.v1.activity.ieo.referral.FomoAwardRecordItem) | repeated |  |






<a name="biss.api.v1.activity.ieo.referral.FomoAwardRecordItem"></a>

### FomoAwardRecordItem
fomo奖励信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| related_time | [uint64](#uint64) |  | 相关时间, UTC timestamp in millisecond |
| amount | [string](#string) |  | 奖励额 |
| type | [FomoAwardType](#biss.api.v1.activity.ieo.referral.FomoAwardType) |  | 类型 |
| single_email | [string](#string) |  | FRT_SINGLE 邮箱 |
| divide_num | [string](#string) |  | FRT_DIVIDE 瓜分人数 |






<a name="biss.api.v1.activity.ieo.referral.FomoRewardInfo"></a>

### FomoRewardInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| cur_time | [uint64](#uint64) |  | 当前时间, UTC timestamp in millisecond |
| related_time | [uint64](#uint64) |  | 相关时间, UTC timestamp in millisecond |
| cur_amount | [string](#string) |  | 当前奖池 |
| cur_amount_acc_round | [string](#string) |  | 当前奖池累计轮次 |
| candidate_uid | [uint64](#uint64) |  | 得奖候选人id |
| candidate_email | [string](#string) |  | 得奖候选人email |
| award_record | [FomoAwardRecord](#biss.api.v1.activity.ieo.referral.FomoAwardRecord) |  | 发奖记录 |






<a name="biss.api.v1.activity.ieo.referral.GlobalStatus"></a>

### GlobalStatus
全局状态


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| cur_time | [uint64](#uint64) |  | 当前时间, UTC timestamp in millisecond |
| start_time | [uint64](#uint64) |  | 邀请活动开始时间, UTC timestamp in millisecond |
| finish_time | [uint64](#uint64) |  | 邀请活动结束时间, UTC timestamp in millisecond |
| cur_limit_reward | [string](#string) |  | 当前阶段额度奖励（为0表示活动未开始或已结束） |
| next_limit_reward | [string](#string) |  | 下一阶段额度奖励（仅在当前阶段额度奖励非0时有效，为0表示活动下一阶段将结束） |
| countdown | [uint64](#uint64) |  | 倒计时, millisecond |






<a name="biss.api.v1.activity.ieo.referral.UserInfo"></a>

### UserInfo
个人信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| uid | [uint64](#uint64) |  | 用户ID |
| referral_id | [string](#string) |  | 邀请码 |
| referral_count | [string](#string) |  | 邀请人数 |
| basic_limit | [string](#string) |  | 基础额度 |
| max_limit | [string](#string) |  | 最大额度 |
| total_limit | [string](#string) |  | 已获额度 |
| referral_limit | [string](#string) |  | 邀请额度（referral_limit = total_limit - basic_limit） |
| limit_pct | [string](#string) |  | 额度获取进度（百分比） |
| qualification | [bool](#bool) |  | 抢购资格 |
| biss_acc_position | [string](#string) |  | BISS累计持仓 |
| biss_acc_position_pct | [string](#string) |  | BISS累计持仓进度（百分比） |
| acc_position_threshold | [string](#string) |  | 累计持仓阀值 |
| fomo_reward | [string](#string) |  | fomo奖励（小数） |





 


<a name="biss.api.v1.activity.ieo.referral.FomoAwardType"></a>

### FomoAwardType
fomo发奖类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| FAT_NONE | 0 |  |
| FAT_SINGLE | 1 | 单人奖励 |
| FAT_DIVIDE | 2 | 瓜分奖励 |


 

 


<a name="biss.api.v1.activity.ieo.referral.Referral"></a>

### Referral


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetGlobalStatus | [.biss.common.trade.Symbol](#biss.common.trade.Symbol) | [GlobalStatus](#biss.api.v1.activity.ieo.referral.GlobalStatus) | 获取全局状态 |
| GetUserInfo | [.biss.common.trade.Symbol](#biss.common.trade.Symbol) | [UserInfo](#biss.api.v1.activity.ieo.referral.UserInfo) | 获取个人信息 |
| GetFomoRewardInfo | [.biss.common.trade.Symbol](#biss.common.trade.Symbol) | [FomoRewardInfo](#biss.api.v1.activity.ieo.referral.FomoRewardInfo) | 获取fomo奖励信息 |

 



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


# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/activity/iostvote.proto](#proto/api/v1/activity/iostvote.proto)
    - [Account](#biss.api.v1.activity.iostvote.Account)
    - [AssetsRecord](#biss.api.v1.activity.iostvote.AssetsRecord)
    - [AssetsRecordItem](#biss.api.v1.activity.iostvote.AssetsRecordItem)
    - [Candidate](#biss.api.v1.activity.iostvote.Candidate)
    - [CandidatesList](#biss.api.v1.activity.iostvote.CandidatesList)
    - [ElectionStatus](#biss.api.v1.activity.iostvote.ElectionStatus)
    - [LeaderboardItem](#biss.api.v1.activity.iostvote.LeaderboardItem)
    - [LeaderboardReq](#biss.api.v1.activity.iostvote.LeaderboardReq)
    - [LeaderboardResp](#biss.api.v1.activity.iostvote.LeaderboardResp)
    - [LeaderboardRewardItem](#biss.api.v1.activity.iostvote.LeaderboardRewardItem)
    - [LeaderboardRewardRecord](#biss.api.v1.activity.iostvote.LeaderboardRewardRecord)
    - [Link](#biss.api.v1.activity.iostvote.Link)
    - [ReferralRewardItem](#biss.api.v1.activity.iostvote.ReferralRewardItem)
    - [ReferralRewardRecord](#biss.api.v1.activity.iostvote.ReferralRewardRecord)
    - [TransferReq](#biss.api.v1.activity.iostvote.TransferReq)
    - [VerifyAccountReq](#biss.api.v1.activity.iostvote.VerifyAccountReq)
    - [VerifyAccountResp](#biss.api.v1.activity.iostvote.VerifyAccountResp)
    - [VoteReq](#biss.api.v1.activity.iostvote.VoteReq)
    - [VotingHistoryItem](#biss.api.v1.activity.iostvote.VotingHistoryItem)
    - [VotingHistoryList](#biss.api.v1.activity.iostvote.VotingHistoryList)
  
    - [AssetsRecordStatus](#biss.api.v1.activity.iostvote.AssetsRecordStatus)
    - [AssetsRecordType](#biss.api.v1.activity.iostvote.AssetsRecordType)
    - [RewardSourceType](#biss.api.v1.activity.iostvote.RewardSourceType)
  
  
    - [IOSTVote](#biss.api.v1.activity.iostvote.IOSTVote)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/activity/iostvote.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/activity/iostvote.proto



<a name="biss.api.v1.activity.iostvote.Account"></a>

### Account
账户信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  | 邮箱 |
| balance | [string](#string) |  | 账户总额（充值划转额度 &#43; 投票收益）（小数） |
| bonus | [string](#string) |  | 投票收益（小数） |
| vote_available | [string](#string) |  | 可用票数（整数） |
| vote_total | [string](#string) |  | 总票数（整数） |
| deposit_addr | [string](#string) |  | 充值地址 |
| deposit_qr | [bytes](#bytes) |  | 充值二维码 |
| invite_code | [string](#string) |  | 邀请码 |
| invite_revenue_cur | [string](#string) |  | 邀请收益，当前已解锁股票数 |
| invite_revenue_max | [string](#string) |  | 邀请收益，最大股票数 |
| invite_revenue_symbol | [string](#string) |  | 邀请收益，股票symbol |






<a name="biss.api.v1.activity.iostvote.AssetsRecord"></a>

### AssetsRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [AssetsRecordItem](#biss.api.v1.activity.iostvote.AssetsRecordItem) | repeated |  |






<a name="biss.api.v1.activity.iostvote.AssetsRecordItem"></a>

### AssetsRecordItem
资产记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 时间, UTC timestamp in millisecond |
| symbol | [string](#string) |  | 标的 |
| type | [AssetsRecordType](#biss.api.v1.activity.iostvote.AssetsRecordType) |  | 类型 |
| qty | [string](#string) |  | 数量 |
| status | [AssetsRecordStatus](#biss.api.v1.activity.iostvote.AssetsRecordStatus) |  | 状态 |
| tx_id | [string](#string) |  | 以下仅在类型为充值时有效

网络交易ID |
| tx_time | [uint64](#uint64) |  | 交易确认时间, UTC timestamp in millisecond |
| status_schedule | [uint32](#uint32) |  | 确认的区块进度,在充值状态中显示 |
| status_confirm | [uint32](#uint32) |  | 确认区块总数，在充值状态中显示 |






<a name="biss.api.v1.activity.iostvote.Candidate"></a>

### Candidate
候选人信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint32](#uint32) |  | 候选人ID |
| rank | [uint32](#uint32) |  | 排名 |
| account | [string](#string) |  | 账户 |
| logo_url | [string](#string) |  | logo URL |
| team_page | [string](#string) |  | 团队页面 |
| location | [string](#string) |  | 位置 |
| type | [string](#string) |  | 类型 |
| elected | [bool](#bool) |  | 是否当选 |
| votes | [string](#string) |  | 票数（整数） |
| percentage | [string](#string) |  | 百分比（精度到0.001%） |
| description | [string](#string) |  | 节点简介 |
| statement | [string](#string) |  | 节点宣言 |
| social_media | [Link](#biss.api.v1.activity.iostvote.Link) | repeated | 社交媒体 |
| interview | [string](#string) |  | 采访视频 |
| today_votes | [string](#string) |  | 当日票数（整数） |






<a name="biss.api.v1.activity.iostvote.CandidatesList"></a>

### CandidatesList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| candidates | [Candidate](#biss.api.v1.activity.iostvote.Candidate) | repeated |  |






<a name="biss.api.v1.activity.iostvote.ElectionStatus"></a>

### ElectionStatus
选举状态


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| close_in | [uint32](#uint32) |  | 距活动结束剩余时间（单位毫秒) |
| total_bonus | [string](#string) |  | 活动发出的总收益（小数） |
| current_time | [uint64](#uint64) |  | 当前时间, UTC timestamp in millisecond |
| referral_start_time | [uint64](#uint64) |  | referral开始时间, UTC timestamp in millisecond |
| referral_end_time | [uint64](#uint64) |  | referral结束时间, UTC timestamp in millisecond |






<a name="biss.api.v1.activity.iostvote.LeaderboardItem"></a>

### LeaderboardItem
排行榜应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rank | [uint32](#uint32) |  | 排名 |
| id | [uint32](#uint32) |  | 候选人ID |
| votes | [string](#string) |  | 统计时间内票数（整数） |






<a name="biss.api.v1.activity.iostvote.LeaderboardReq"></a>

### LeaderboardReq
排行榜请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| start_time | [uint64](#uint64) |  | 统计开始时间（含）, UTC timestamp in millisecond |
| end_time | [uint64](#uint64) |  | 统计结束时间（不含）， UTC timestamp in millisecond |
| number | [uint32](#uint32) |  | 排行榜条目数量 |






<a name="biss.api.v1.activity.iostvote.LeaderboardResp"></a>

### LeaderboardResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [LeaderboardItem](#biss.api.v1.activity.iostvote.LeaderboardItem) | repeated |  |






<a name="biss.api.v1.activity.iostvote.LeaderboardRewardItem"></a>

### LeaderboardRewardItem
获取排行榜活动用户奖励记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 投票时间, UTC timestamp in millisecond |
| votes | [string](#string) |  | 投票数量（整数） |
| type | [RewardSourceType](#biss.api.v1.activity.iostvote.RewardSourceType) |  | 奖励来源类型 |
| reward_number | [string](#string) |  | 奖励数量 |
| reward_time | [uint64](#uint64) |  | 奖励时间, UTC timestamp in millisecond |






<a name="biss.api.v1.activity.iostvote.LeaderboardRewardRecord"></a>

### LeaderboardRewardRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [LeaderboardRewardItem](#biss.api.v1.activity.iostvote.LeaderboardRewardItem) | repeated |  |






<a name="biss.api.v1.activity.iostvote.Link"></a>

### Link
超链接


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  | 超链接名称 |
| url | [string](#string) |  | 超链接URL |






<a name="biss.api.v1.activity.iostvote.ReferralRewardItem"></a>

### ReferralRewardItem
获取Referral活动用户奖励记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 被邀请人 注册时间, UTC timestamp in millisecond |
| email | [string](#string) |  | 被邀请人 账户 |
| votes | [string](#string) |  | 被邀请人 投票数量（整数） |
| reward | [string](#string) |  | 邀请奖励 |






<a name="biss.api.v1.activity.iostvote.ReferralRewardRecord"></a>

### ReferralRewardRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total_number | [uint32](#uint32) |  | 被邀请人总数 |
| total_reward | [string](#string) |  | 邀请奖励总数 |
| items | [ReferralRewardItem](#biss.api.v1.activity.iostvote.ReferralRewardItem) | repeated |  |






<a name="biss.api.v1.activity.iostvote.TransferReq"></a>

### TransferReq
划转请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| qty | [string](#string) |  | 数量（小数） |






<a name="biss.api.v1.activity.iostvote.VerifyAccountReq"></a>

### VerifyAccountReq
验证账户请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  | 账户邮箱 |
| address | [string](#string) |  | 账户IOST充值地址 |






<a name="biss.api.v1.activity.iostvote.VerifyAccountResp"></a>

### VerifyAccountResp
验证账户应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| result | [bool](#bool) |  | 验证结果 |






<a name="biss.api.v1.activity.iostvote.VoteReq"></a>

### VoteReq
投票请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| vote_to | [uint32](#uint32) |  | 候选人ID |
| qty | [string](#string) |  | 数量（整数） |






<a name="biss.api.v1.activity.iostvote.VotingHistoryItem"></a>

### VotingHistoryItem
投票记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 时间 |
| votes | [string](#string) |  | 数量（整数） |
| votes_to | [uint32](#uint32) |  | 候选人ID |
| votes_account | [string](#string) |  | 候选人名称 |






<a name="biss.api.v1.activity.iostvote.VotingHistoryList"></a>

### VotingHistoryList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [VotingHistoryItem](#biss.api.v1.activity.iostvote.VotingHistoryItem) | repeated |  |





 


<a name="biss.api.v1.activity.iostvote.AssetsRecordStatus"></a>

### AssetsRecordStatus
资产记录状态

| Name | Number | Description |
| ---- | ------ | ----------- |
| ARS_NONE | 0 |  |
| ARS_CONFIRMING | 1 | 确认中 |
| ARS_DONE | 2 | 已完成 |



<a name="biss.api.v1.activity.iostvote.AssetsRecordType"></a>

### AssetsRecordType
资产记录类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| ART_NONE | 0 |  |
| ART_DEPOSIT | 1 | 充值 |
| ART_TRANSFER | 2 | 划转 |



<a name="biss.api.v1.activity.iostvote.RewardSourceType"></a>

### RewardSourceType
奖励来源类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| RST_NONE | 0 |  |
| RST_DIV_FIRST | 1 | 瓜分第一名 |
| RST_DIV_SECOND | 2 | 瓜分第二名 |
| RST_DIV_THIRD | 3 | 瓜分第三名 |
| RST_FIRST_VOTE | 4 | 首投奖励 |


 

 


<a name="biss.api.v1.activity.iostvote.IOSTVote"></a>

### IOSTVote


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetElectionStatus | [.biss.common.Empty](#biss.common.Empty) | [ElectionStatus](#biss.api.v1.activity.iostvote.ElectionStatus) | 获取选举状态 |
| GetCandidatesList | [.biss.common.Empty](#biss.common.Empty) | [CandidatesList](#biss.api.v1.activity.iostvote.CandidatesList) | 获取候选人信息 |
| GetAccount | [.biss.common.Empty](#biss.common.Empty) | [Account](#biss.api.v1.activity.iostvote.Account) | 获取账户信息 |
| GetVotingHistory | [.biss.common.Empty](#biss.common.Empty) | [VotingHistoryList](#biss.api.v1.activity.iostvote.VotingHistoryList) | 获取投票记录 |
| Vote | [VoteReq](#biss.api.v1.activity.iostvote.VoteReq) | [.biss.common.Empty](#biss.common.Empty) | 投票 |
| Transfer | [TransferReq](#biss.api.v1.activity.iostvote.TransferReq) | [.biss.common.Empty](#biss.common.Empty) | 划转 |
| GetAssetsRecord | [.biss.common.Empty](#biss.common.Empty) | [AssetsRecord](#biss.api.v1.activity.iostvote.AssetsRecord) | 获取资产记录（包含充值和划转） |
| VerifyAccount | [VerifyAccountReq](#biss.api.v1.activity.iostvote.VerifyAccountReq) | [VerifyAccountResp](#biss.api.v1.activity.iostvote.VerifyAccountResp) | 验证账户 |
| GetLeaderboardRewardRecord | [.biss.common.Empty](#biss.common.Empty) | [LeaderboardRewardRecord](#biss.api.v1.activity.iostvote.LeaderboardRewardRecord) | 获取排行榜活动用户奖励记录 |
| GetLeaderboard | [LeaderboardReq](#biss.api.v1.activity.iostvote.LeaderboardReq) | [LeaderboardResp](#biss.api.v1.activity.iostvote.LeaderboardResp) | 获取排行榜 |
| GetReferralRewardRecord | [.biss.common.Empty](#biss.common.Empty) | [ReferralRewardRecord](#biss.api.v1.activity.iostvote.ReferralRewardRecord) | 获取Referral活动用户奖励记录 |

 



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


# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/activity/iostmainnet.proto](#proto/api/v1/activity/iostmainnet.proto)
    - [Account](#biss.api.v1.activity.iostmainnet.Account)
    - [CancelRecord](#biss.api.v1.activity.iostmainnet.CancelRecord)
    - [CancelRecordItem](#biss.api.v1.activity.iostmainnet.CancelRecordItem)
    - [CandidateItem](#biss.api.v1.activity.iostmainnet.CandidateItem)
    - [CandidatesList](#biss.api.v1.activity.iostmainnet.CandidatesList)
    - [DepositRecord](#biss.api.v1.activity.iostmainnet.DepositRecord)
    - [DepositRecordItem](#biss.api.v1.activity.iostmainnet.DepositRecordItem)
    - [EarlyBirdVotingRewardRecord](#biss.api.v1.activity.iostmainnet.EarlyBirdVotingRewardRecord)
    - [InviteInfo](#biss.api.v1.activity.iostmainnet.InviteInfo)
    - [LeaderboardRewardItem](#biss.api.v1.activity.iostmainnet.LeaderboardRewardItem)
    - [LeaderboardRewardRecord](#biss.api.v1.activity.iostmainnet.LeaderboardRewardRecord)
    - [Link](#biss.api.v1.activity.iostmainnet.Link)
    - [QuarterlyRewardRecord](#biss.api.v1.activity.iostmainnet.QuarterlyRewardRecord)
    - [QuarterlyRewardRecordItem](#biss.api.v1.activity.iostmainnet.QuarterlyRewardRecordItem)
    - [ReferralRewardRecord](#biss.api.v1.activity.iostmainnet.ReferralRewardRecord)
    - [ReferralRewardRecordItem](#biss.api.v1.activity.iostmainnet.ReferralRewardRecordItem)
    - [TransferRecord](#biss.api.v1.activity.iostmainnet.TransferRecord)
    - [TransferRecordItem](#biss.api.v1.activity.iostmainnet.TransferRecordItem)
    - [TransferReq](#biss.api.v1.activity.iostmainnet.TransferReq)
    - [VoteReq](#biss.api.v1.activity.iostmainnet.VoteReq)
    - [VotingRecord](#biss.api.v1.activity.iostmainnet.VotingRecord)
    - [VotingRecordItem](#biss.api.v1.activity.iostmainnet.VotingRecordItem)
    - [VotingRewardRecord](#biss.api.v1.activity.iostmainnet.VotingRewardRecord)
    - [VotingRewardRecordItem](#biss.api.v1.activity.iostmainnet.VotingRewardRecordItem)
    - [VotingStatisticsItem](#biss.api.v1.activity.iostmainnet.VotingStatisticsItem)
    - [VotingStatisticsList](#biss.api.v1.activity.iostmainnet.VotingStatisticsList)
  
    - [LeaderboardRewardType](#biss.api.v1.activity.iostmainnet.LeaderboardRewardType)
    - [TransferType](#biss.api.v1.activity.iostmainnet.TransferType)
    - [VoteOperateType](#biss.api.v1.activity.iostmainnet.VoteOperateType)
  
  
    - [IOSTMainnet](#biss.api.v1.activity.iostmainnet.IOSTMainnet)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/activity/iostmainnet.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/activity/iostmainnet.proto



<a name="biss.api.v1.activity.iostmainnet.Account"></a>

### Account
账户信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  | 邮箱 |
| assets_total | [string](#string) |  | 总资产（小数）（正向充值&#43;正向划转&#43;收益）（可用资产&#43;冻结资产&lt;占用票数&gt;） |
| assets_available | [string](#string) |  | 可用资产（小数） |
| assets_reward | [string](#string) |  | 奖励资产（小数） |
| vote_total | [string](#string) |  | 总票数（整数）（总资产取整） |
| vote_available | [string](#string) |  | 可用票数（整数）（可用资产取整） |
| vote_occupy | [string](#string) |  | 占用票数（整数）(在投&#43;赎回) |
| vote_redemption | [string](#string) |  | 赎回票数（整数） |






<a name="biss.api.v1.activity.iostmainnet.CancelRecord"></a>

### CancelRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [CancelRecordItem](#biss.api.v1.activity.iostmainnet.CancelRecordItem) | repeated |  |






<a name="biss.api.v1.activity.iostmainnet.CancelRecordItem"></a>

### CancelRecordItem
取消记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 时间, UTC timestamp in millisecond |
| name | [string](#string) |  | 候选人名称 |
| votes | [string](#string) |  | 票数（整数） |
| redeem_time | [uint64](#uint64) |  | 赎回时间, UTC timestamp in millisecond |






<a name="biss.api.v1.activity.iostmainnet.CandidateItem"></a>

### CandidateItem
候选人信息列表


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint32](#uint32) |  | 候选人ID |
| rank | [uint32](#uint32) |  | 排名 |
| name | [string](#string) |  | 名称 |
| address | [string](#string) |  | 主网账号地址 |
| logo_url | [string](#string) |  | logo URL |
| team_page | [string](#string) |  | 团队页面 |
| location | [string](#string) |  | 位置 |
| type | [string](#string) |  | 类型 |
| elected | [bool](#bool) |  | 是否当选 |
| votes | [string](#string) |  | 票数（整数） |
| percentage | [string](#string) |  | 百分比（精度到0.001%） |
| description | [string](#string) |  | 节点简介 |
| statement | [string](#string) |  | 节点宣言 |
| social_media | [Link](#biss.api.v1.activity.iostmainnet.Link) | repeated | 社交媒体 |
| interview | [string](#string) |  | 采访视频 |
| is_online | [bool](#bool) |  | 是否在线 |
| can_vote | [bool](#bool) |  | 可以投票 |
| can_cancel | [bool](#bool) |  | 可以取消 |






<a name="biss.api.v1.activity.iostmainnet.CandidatesList"></a>

### CandidatesList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [CandidateItem](#biss.api.v1.activity.iostmainnet.CandidateItem) | repeated |  |






<a name="biss.api.v1.activity.iostmainnet.DepositRecord"></a>

### DepositRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [DepositRecordItem](#biss.api.v1.activity.iostmainnet.DepositRecordItem) | repeated |  |






<a name="biss.api.v1.activity.iostmainnet.DepositRecordItem"></a>

### DepositRecordItem
充值记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 时间, UTC timestamp in millisecond |
| qty | [string](#string) |  | 数量（小数） |
| tx_id | [string](#string) |  | 网络交易ID |
| tx_time | [uint64](#uint64) |  | 交易确认时间, UTC timestamp in millisecond |






<a name="biss.api.v1.activity.iostmainnet.EarlyBirdVotingRewardRecord"></a>

### EarlyBirdVotingRewardRecord
早鸟投票奖励记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| reward_time_period | [string](#string) |  | 奖励时间段 |
| votes | [string](#string) |  | 票数（整数） |
| reward | [string](#string) |  | 奖励（小数） |






<a name="biss.api.v1.activity.iostmainnet.InviteInfo"></a>

### InviteInfo
邀请信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| code | [string](#string) |  | 邀请码 |
| cur | [string](#string) |  | 邀请收益，当前已解锁股票数 |
| max | [string](#string) |  | 邀请收益，最大解锁股票数 |
| symbol | [string](#string) |  | 邀请收益，股票symbol |






<a name="biss.api.v1.activity.iostmainnet.LeaderboardRewardItem"></a>

### LeaderboardRewardItem
Leaderboard奖励记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 投票时间, UTC timestamp in millisecond |
| votes | [string](#string) |  | 票数（整数） |
| type | [LeaderboardRewardType](#biss.api.v1.activity.iostmainnet.LeaderboardRewardType) |  | 奖励类型 |
| reward | [string](#string) |  | 奖励（小数） |
| reward_time | [uint64](#uint64) |  | 奖励时间, UTC timestamp in millisecond |






<a name="biss.api.v1.activity.iostmainnet.LeaderboardRewardRecord"></a>

### LeaderboardRewardRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [LeaderboardRewardItem](#biss.api.v1.activity.iostmainnet.LeaderboardRewardItem) | repeated |  |






<a name="biss.api.v1.activity.iostmainnet.Link"></a>

### Link
超链接


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  | 超链接名称 |
| url | [string](#string) |  | 超链接URL |






<a name="biss.api.v1.activity.iostmainnet.QuarterlyRewardRecord"></a>

### QuarterlyRewardRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [QuarterlyRewardRecordItem](#biss.api.v1.activity.iostmainnet.QuarterlyRewardRecordItem) | repeated |  |






<a name="biss.api.v1.activity.iostmainnet.QuarterlyRewardRecordItem"></a>

### QuarterlyRewardRecordItem
季度奖励记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 奖励时间, UTC timestamp in millisecond |
| can_id | [uint32](#uint32) |  | 候选人ID |
| reward | [string](#string) |  | 奖励 |
| comments | [string](#string) |  | 备注 |






<a name="biss.api.v1.activity.iostmainnet.ReferralRewardRecord"></a>

### ReferralRewardRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [ReferralRewardRecordItem](#biss.api.v1.activity.iostmainnet.ReferralRewardRecordItem) | repeated |  |






<a name="biss.api.v1.activity.iostmainnet.ReferralRewardRecordItem"></a>

### ReferralRewardRecordItem
Referral奖励记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 被邀请人 注册时间, UTC timestamp in millisecond |
| email | [string](#string) |  | 被邀请人 账户 |
| votes | [string](#string) |  | 被邀请人 投票数量（整数） |
| reward | [string](#string) |  | 邀请奖励 |






<a name="biss.api.v1.activity.iostmainnet.TransferRecord"></a>

### TransferRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [TransferRecordItem](#biss.api.v1.activity.iostmainnet.TransferRecordItem) | repeated |  |






<a name="biss.api.v1.activity.iostmainnet.TransferRecordItem"></a>

### TransferRecordItem
划转记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 时间, UTC timestamp in millisecond |
| type | [TransferType](#biss.api.v1.activity.iostmainnet.TransferType) |  | 类型 |
| qty | [string](#string) |  | 数量（小数） |






<a name="biss.api.v1.activity.iostmainnet.TransferReq"></a>

### TransferReq
划转请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [TransferType](#biss.api.v1.activity.iostmainnet.TransferType) |  | 类型 |
| qty | [string](#string) |  | 数量（小数） |






<a name="biss.api.v1.activity.iostmainnet.VoteReq"></a>

### VoteReq
投票请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [VoteOperateType](#biss.api.v1.activity.iostmainnet.VoteOperateType) |  | 类型 |
| vote_to | [uint32](#uint32) |  | 候选人ID |
| votes | [string](#string) |  | 票数（整数） |






<a name="biss.api.v1.activity.iostmainnet.VotingRecord"></a>

### VotingRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [VotingRecordItem](#biss.api.v1.activity.iostmainnet.VotingRecordItem) | repeated |  |






<a name="biss.api.v1.activity.iostmainnet.VotingRecordItem"></a>

### VotingRecordItem
投票记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 时间, UTC timestamp in millisecond |
| name | [string](#string) |  | 候选人名称 |
| votes | [string](#string) |  | 票数（整数） |






<a name="biss.api.v1.activity.iostmainnet.VotingRewardRecord"></a>

### VotingRewardRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [VotingRewardRecordItem](#biss.api.v1.activity.iostmainnet.VotingRewardRecordItem) | repeated |  |






<a name="biss.api.v1.activity.iostmainnet.VotingRewardRecordItem"></a>

### VotingRewardRecordItem
主网投票奖励记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| reward_time_date | [string](#string) |  | 奖励时间日期 |
| reward | [string](#string) |  | 奖励（小数） |






<a name="biss.api.v1.activity.iostmainnet.VotingStatisticsItem"></a>

### VotingStatisticsItem
投票信息列表（针对候选人的在投票数）


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| vote_to | [uint32](#uint32) |  | 候选人ID |
| votes | [string](#string) |  | 票数（整数）（在投） |






<a name="biss.api.v1.activity.iostmainnet.VotingStatisticsList"></a>

### VotingStatisticsList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [VotingStatisticsItem](#biss.api.v1.activity.iostmainnet.VotingStatisticsItem) | repeated |  |





 


<a name="biss.api.v1.activity.iostmainnet.LeaderboardRewardType"></a>

### LeaderboardRewardType
Leaderboard奖励类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| LRT_NONE | 0 |  |
| LRT_DIV_FIRST | 1 | 瓜分第一名 |
| LRT_DIV_SECOND | 2 | 瓜分第二名 |
| LRT_DIV_THIRD | 3 | 瓜分第三名 |
| LRT_FIRST_VOTE | 4 | 首投奖励 |



<a name="biss.api.v1.activity.iostmainnet.TransferType"></a>

### TransferType
划转类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| TT_NONE | 0 |  |
| TT_CC_2_IOST | 1 | 币币 到 IOST |
| TT_IOST_2_CC | 2 | IOST 到 币币 |



<a name="biss.api.v1.activity.iostmainnet.VoteOperateType"></a>

### VoteOperateType
投票操作类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| VOT_NONE | 0 |  |
| VOT_VOTE | 1 | 投票 |
| VOT_CANCEL | 2 | 取消 |


 

 


<a name="biss.api.v1.activity.iostmainnet.IOSTMainnet"></a>

### IOSTMainnet


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetCandidatesList | [.biss.common.Empty](#biss.common.Empty) | [CandidatesList](#biss.api.v1.activity.iostmainnet.CandidatesList) | 信息 获取候选人信息列表 |
| GetAccount | [.biss.common.Empty](#biss.common.Empty) | [Account](#biss.api.v1.activity.iostmainnet.Account) | 获取账户信息 |
| GetInviteInfo | [.biss.common.Empty](#biss.common.Empty) | [InviteInfo](#biss.api.v1.activity.iostmainnet.InviteInfo) | 获取邀请信息 |
| GetVotingStatisticsList | [.biss.common.Empty](#biss.common.Empty) | [VotingStatisticsList](#biss.api.v1.activity.iostmainnet.VotingStatisticsList) | 获取投票统计列表（针对候选人的在投票数） |
| Transfer | [TransferReq](#biss.api.v1.activity.iostmainnet.TransferReq) | [.biss.common.Empty](#biss.common.Empty) | 操作 划转 |
| Vote | [VoteReq](#biss.api.v1.activity.iostmainnet.VoteReq) | [.biss.common.Empty](#biss.common.Empty) | 投票 |
| GetDepositRecord | [.biss.common.Empty](#biss.common.Empty) | [DepositRecord](#biss.api.v1.activity.iostmainnet.DepositRecord) | 记录 获取充值记录 |
| GetTransferRecord | [.biss.common.Empty](#biss.common.Empty) | [TransferRecord](#biss.api.v1.activity.iostmainnet.TransferRecord) | 获取划转记录 |
| GetVotingRecord | [.biss.common.Empty](#biss.common.Empty) | [VotingRecord](#biss.api.v1.activity.iostmainnet.VotingRecord) | 获取投票记录 |
| GetCancelRecord | [.biss.common.Empty](#biss.common.Empty) | [CancelRecord](#biss.api.v1.activity.iostmainnet.CancelRecord) | 获取取消记录 |
| GetVotingRewardRecord | [.biss.common.Empty](#biss.common.Empty) | [VotingRewardRecord](#biss.api.v1.activity.iostmainnet.VotingRewardRecord) | 获取主网投票奖励记录 |
| GetEarlyBirdVotingRewardRecord | [.biss.common.Empty](#biss.common.Empty) | [EarlyBirdVotingRewardRecord](#biss.api.v1.activity.iostmainnet.EarlyBirdVotingRewardRecord) | 获取早鸟投票奖励记录 |
| GetLeaderboardRewardRecord | [.biss.common.Empty](#biss.common.Empty) | [LeaderboardRewardRecord](#biss.api.v1.activity.iostmainnet.LeaderboardRewardRecord) | 获取Leaderboard奖励记录 |
| GetReferralRewardRecord | [.biss.common.Empty](#biss.common.Empty) | [ReferralRewardRecord](#biss.api.v1.activity.iostmainnet.ReferralRewardRecord) | 获取Referral奖励记录 |
| GetQuarterlyRewardRecord | [.biss.common.Empty](#biss.common.Empty) | [QuarterlyRewardRecord](#biss.api.v1.activity.iostmainnet.QuarterlyRewardRecord) | 获取季度奖励记录 |

 



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


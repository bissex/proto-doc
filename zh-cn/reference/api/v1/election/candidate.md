# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/election/candidate.proto](#proto/api/v1/election/candidate.proto)
    - [CandidateConfig](#biss.api.v1.election.CandidateConfig)
    - [CandidateControl](#biss.api.v1.election.CandidateControl)
    - [CandidateItem](#biss.api.v1.election.CandidateItem)
    - [CandidateVotes](#biss.api.v1.election.CandidateVotes)
    - [CandidatesList](#biss.api.v1.election.CandidatesList)
    - [Leaderboard](#biss.api.v1.election.Leaderboard)
    - [LeaderboardItem](#biss.api.v1.election.LeaderboardItem)
    - [LeaderboardReq](#biss.api.v1.election.LeaderboardReq)
    - [Link](#biss.api.v1.election.Link)
  
    - [LeaderboardCandidateFilter](#biss.api.v1.election.LeaderboardCandidateFilter)
    - [LeaderboardTimeFilter](#biss.api.v1.election.LeaderboardTimeFilter)
    - [LeaderboardVotesFilter](#biss.api.v1.election.LeaderboardVotesFilter)
  
  
    - [CandidateSvc](#biss.api.v1.election.CandidateSvc)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/election/candidate.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/election/candidate.proto



<a name="biss.api.v1.election.CandidateConfig"></a>

### CandidateConfig
候选人配置信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint32](#uint32) |  | 候选人id |
| uid | [uint64](#uint64) |  | BISS uid |
| name | [string](#string) |  | 名称 |
| mainnet_address | [string](#string) |  | 主网账号地址(仅在主网阶段有效) |
| logo_url | [string](#string) |  | logo URL |
| team_page | [string](#string) |  | 团队页面 |
| location | [string](#string) |  | 位置 |
| type | [string](#string) |  | 类型 |
| description | [string](#string) |  | 简介 |
| statement | [string](#string) |  | 宣言 |
| social_media | [Link](#biss.api.v1.election.Link) | repeated | 社交媒体 |






<a name="biss.api.v1.election.CandidateControl"></a>

### CandidateControl
候选人控制信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| is_online | [bool](#bool) |  | 是否在线 |
| can_vote | [bool](#bool) |  | 可以投票 |
| can_cancel | [bool](#bool) |  | 可以取消 |






<a name="biss.api.v1.election.CandidateItem"></a>

### CandidateItem
候选人列表


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| config | [CandidateConfig](#biss.api.v1.election.CandidateConfig) |  | 配置信息 |
| votes | [CandidateVotes](#biss.api.v1.election.CandidateVotes) |  | 投票信息 |
| control | [CandidateControl](#biss.api.v1.election.CandidateControl) |  | 控制信息 |






<a name="biss.api.v1.election.CandidateVotes"></a>

### CandidateVotes
候选人投票信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rank | [uint32](#uint32) |  | 排名 |
| elected | [bool](#bool) |  | 是否当选 |
| votes | [string](#string) |  | 票数 |
| percentage | [string](#string) |  | 百分比（精度到0.001%） |






<a name="biss.api.v1.election.CandidatesList"></a>

### CandidatesList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [CandidateItem](#biss.api.v1.election.CandidateItem) | repeated |  |






<a name="biss.api.v1.election.Leaderboard"></a>

### Leaderboard



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [LeaderboardItem](#biss.api.v1.election.LeaderboardItem) | repeated |  |






<a name="biss.api.v1.election.LeaderboardItem"></a>

### LeaderboardItem
排行榜


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rank | [uint32](#uint32) |  | 排名 |
| id | [uint32](#uint32) |  | 候选人id |
| votes | [string](#string) |  | 票数 |






<a name="biss.api.v1.election.LeaderboardReq"></a>

### LeaderboardReq
排行榜请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| time | [LeaderboardTimeFilter](#biss.api.v1.election.LeaderboardTimeFilter) |  | 时间过滤器 |
| candidate | [LeaderboardCandidateFilter](#biss.api.v1.election.LeaderboardCandidateFilter) |  | 候选人过滤器 |
| votes | [LeaderboardVotesFilter](#biss.api.v1.election.LeaderboardVotesFilter) |  | 票数过滤器 |
| number | [uint32](#uint32) |  | 条数 |






<a name="biss.api.v1.election.Link"></a>

### Link
超链接


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  | 名称 |
| url | [string](#string) |  | URL |





 


<a name="biss.api.v1.election.LeaderboardCandidateFilter"></a>

### LeaderboardCandidateFilter
排行榜候选人过滤器

| Name | Number | Description |
| ---- | ------ | ----------- |
| LCF_NONE | 0 |  |
| LCF_ALL | 1 | 全部 |
| LCF_ELECTED | 2 | 当选 |
| LCF_DESIGNATED_DAY_NEWLY_ELECTED | 3 | 当日新当选 |



<a name="biss.api.v1.election.LeaderboardTimeFilter"></a>

### LeaderboardTimeFilter
排行榜时间过滤器

| Name | Number | Description |
| ---- | ------ | ----------- |
| LTF_NONE | 0 |  |
| LTF_TODAY | 1 | 今日 |
| LTF_YESTERDAY | 2 | 昨日 |



<a name="biss.api.v1.election.LeaderboardVotesFilter"></a>

### LeaderboardVotesFilter
排行榜票数过滤器

| Name | Number | Description |
| ---- | ------ | ----------- |
| LVF_NONE | 0 |  |
| LVF_DESIGNATED_DAY_VOTES | 1 | 当日票数 |
| LVF_TOTAL_VOTES | 2 | 总票数 |


 

 


<a name="biss.api.v1.election.CandidateSvc"></a>

### CandidateSvc


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetCandidatesList | [.biss.common.trade.Symbol](#biss.common.trade.Symbol) | [CandidatesList](#biss.api.v1.election.CandidatesList) | 获取候选人列表 |
| GetLeaderboard | [LeaderboardReq](#biss.api.v1.election.LeaderboardReq) | [Leaderboard](#biss.api.v1.election.Leaderboard) | 获取排行榜 |

 



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


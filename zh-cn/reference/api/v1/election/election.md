# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/election/election.proto](#proto/api/v1/election/election.proto)
    - [ElectionConfig](#biss.api.v1.election.ElectionConfig)
    - [ElectionConfigList](#biss.api.v1.election.ElectionConfigList)
    - [ElectionStatus](#biss.api.v1.election.ElectionStatus)
  
    - [ElectionPhase](#biss.api.v1.election.ElectionPhase)
  
  
    - [ElectionSvc](#biss.api.v1.election.ElectionSvc)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/election/election.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/election/election.proto



<a name="biss.api.v1.election.ElectionConfig"></a>

### ElectionConfig
选举配置列表


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| priority | [uint32](#uint32) |  | 优先级 |
| phase | [ElectionPhase](#biss.api.v1.election.ElectionPhase) |  | 选举阶段 |
| min_num_votes | [uint64](#uint64) |  | 最小投票数量(为0表示无限制) |
| elected_threshold | [uint64](#uint64) |  | 当选阈值(仅在测试网阶段有效) |
| can_vote | [bool](#bool) |  | 可以投票 |
| can_cancel | [bool](#bool) |  | 可以取消 |
| can_cc_2_election | [bool](#bool) |  | 可以转入 |
| can_election_2_cc | [bool](#bool) |  | 可以转出 |






<a name="biss.api.v1.election.ElectionConfigList"></a>

### ElectionConfigList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [ElectionConfig](#biss.api.v1.election.ElectionConfig) | repeated |  |






<a name="biss.api.v1.election.ElectionStatus"></a>

### ElectionStatus
获取选举状态


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| cur_time | [uint64](#uint64) |  | 当前时间(UTC timestamp in millisecond) |
| total_reward | [string](#string) |  | 所有收益类型的收益总和 |





 


<a name="biss.api.v1.election.ElectionPhase"></a>

### ElectionPhase
选举阶段

| Name | Number | Description |
| ---- | ------ | ----------- |
| EP_NONE | 0 |  |
| EP_TESTNET | 1 | 测试网 |
| EP_MAINNET | 2 | 主网 |


 

 


<a name="biss.api.v1.election.ElectionSvc"></a>

### ElectionSvc


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetElectionConfigList | [.biss.common.Empty](#biss.common.Empty) | [ElectionConfigList](#biss.api.v1.election.ElectionConfigList) | 获取选举配置列表 |
| GetElectionStatus | [.biss.common.trade.Symbol](#biss.common.trade.Symbol) | [ElectionStatus](#biss.api.v1.election.ElectionStatus) | 获取选举状态 |

 



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


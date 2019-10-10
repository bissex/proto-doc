# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/election/vote.proto](#proto/api/v1/election/vote.proto)
    - [VoteReq](#biss.api.v1.election.VoteReq)
    - [VotingRecord](#biss.api.v1.election.VotingRecord)
    - [VotingRecordItem](#biss.api.v1.election.VotingRecordItem)
  
    - [VoteOperateType](#biss.api.v1.election.VoteOperateType)
  
  
    - [VoteSvc](#biss.api.v1.election.VoteSvc)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/election/vote.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/election/vote.proto



<a name="biss.api.v1.election.VoteReq"></a>

### VoteReq
投票请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| type | [VoteOperateType](#biss.api.v1.election.VoteOperateType) |  | 类型 |
| vote_to | [uint32](#uint32) |  | 候选人id |
| votes | [string](#string) |  | 票数 |






<a name="biss.api.v1.election.VotingRecord"></a>

### VotingRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [VotingRecordItem](#biss.api.v1.election.VotingRecordItem) | repeated |  |






<a name="biss.api.v1.election.VotingRecordItem"></a>

### VotingRecordItem
投票记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 时间(UTC timestamp in millisecond) |
| name | [string](#string) |  | 候选人 |
| votes | [string](#string) |  | 票数 |





 


<a name="biss.api.v1.election.VoteOperateType"></a>

### VoteOperateType
投票操作类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| VOT_NONE | 0 |  |
| VOT_VOTE | 1 | 投票 |
| VOT_CANCEL | 2 | 取消 |


 

 


<a name="biss.api.v1.election.VoteSvc"></a>

### VoteSvc


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Vote | [VoteReq](#biss.api.v1.election.VoteReq) | [.biss.common.Empty](#biss.common.Empty) | 投票 |
| GetVotingRecord | [.biss.common.trade.Symbol](#biss.common.trade.Symbol) | [VotingRecord](#biss.api.v1.election.VotingRecord) | 获取投票记录 |

 



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


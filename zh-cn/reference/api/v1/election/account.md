# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/election/account.proto](#proto/api/v1/election/account.proto)
    - [Account](#biss.api.v1.election.Account)
    - [Assets](#biss.api.v1.election.Assets)
  
  
  
    - [AccountSvc](#biss.api.v1.election.AccountSvc)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/election/account.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/election/account.proto



<a name="biss.api.v1.election.Account"></a>

### Account
账户


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  | 邮箱 |
| is_candidate | [bool](#bool) |  | 是否候选人身份 |
| candidate_id | [uint32](#uint32) |  | 候选人id(仅在有候选人身份时有效) |
| assets | [Assets](#biss.api.v1.election.Assets) |  | 资产 |






<a name="biss.api.v1.election.Assets"></a>

### Assets
资产


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| assets_total | [string](#string) |  | 总资产(正向划转&#43;奖励)(可用资产&#43;冻结资产&lt;占用票数&gt;) |
| assets_available | [string](#string) |  | 可用资产 |
| vote_total | [string](#string) |  | 总票数(总资产取整) |
| vote_available | [string](#string) |  | 可用票数(可用资产取整) |
| vote_occupy | [string](#string) |  | 占用票数(在投&#43;赎回) |
| vote_redemption | [string](#string) |  | 赎回票数 |
| reward_total | [string](#string) |  | 总奖励 |
| reward_voter | [string](#string) |  | 投票者奖励 |
| reward_candidate | [string](#string) |  | 候选人奖励 |





 

 

 


<a name="biss.api.v1.election.AccountSvc"></a>

### AccountSvc


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetAccount | [.biss.common.trade.Symbol](#biss.common.trade.Symbol) | [Account](#biss.api.v1.election.Account) | 获取账户 |

 



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


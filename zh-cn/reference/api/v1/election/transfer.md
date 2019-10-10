# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/election/transfer.proto](#proto/api/v1/election/transfer.proto)
    - [TransferRecord](#biss.api.v1.election.TransferRecord)
    - [TransferRecordItem](#biss.api.v1.election.TransferRecordItem)
    - [TransferReq](#biss.api.v1.election.TransferReq)
  
    - [TransferType](#biss.api.v1.election.TransferType)
  
  
    - [TransferSvc](#biss.api.v1.election.TransferSvc)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/election/transfer.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/election/transfer.proto



<a name="biss.api.v1.election.TransferRecord"></a>

### TransferRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [TransferRecordItem](#biss.api.v1.election.TransferRecordItem) | repeated |  |






<a name="biss.api.v1.election.TransferRecordItem"></a>

### TransferRecordItem
划转记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 时间(UTC timestamp in millisecond) |
| type | [TransferType](#biss.api.v1.election.TransferType) |  | 类型 |
| qty | [string](#string) |  | 数量 |






<a name="biss.api.v1.election.TransferReq"></a>

### TransferReq
划转请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| type | [TransferType](#biss.api.v1.election.TransferType) |  | 类型 |
| qty | [string](#string) |  | 数量 |





 


<a name="biss.api.v1.election.TransferType"></a>

### TransferType
划转类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| TT_NONE | 0 |  |
| TT_CC_2_ELECTION | 1 | 币币 到 选举 |
| TT_ELECTION_2_CC | 2 | 选举 到 币币 |


 

 


<a name="biss.api.v1.election.TransferSvc"></a>

### TransferSvc


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Transfer | [TransferReq](#biss.api.v1.election.TransferReq) | [.biss.common.Empty](#biss.common.Empty) | 划转 |
| GetTransferRecord | [.biss.common.trade.Symbol](#biss.common.trade.Symbol) | [TransferRecord](#biss.api.v1.election.TransferRecord) | 获取划转记录 |

 



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


# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/csc/assets.proto](#proto/api/v1/csc/assets.proto)
    - [Asset](#biss.api.v1.csc.asset.Asset)
    - [AssetsResp](#biss.api.v1.csc.asset.AssetsResp)
    - [LegalValue](#biss.api.v1.csc.asset.LegalValue)
    - [Position](#biss.api.v1.csc.asset.Position)
    - [PositionListResp](#biss.api.v1.csc.asset.PositionListResp)
    - [TransferHistoricalRecord](#biss.api.v1.csc.asset.TransferHistoricalRecord)
    - [TransferHistoryReq](#biss.api.v1.csc.asset.TransferHistoryReq)
    - [TransferHistoryResp](#biss.api.v1.csc.asset.TransferHistoryResp)
    - [TransferReq](#biss.api.v1.csc.asset.TransferReq)
  
    - [TransferDirect](#biss.api.v1.csc.asset.TransferDirect)
  
  
    - [Assets](#biss.api.v1.csc.asset.Assets)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/csc/assets.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/csc/assets.proto



<a name="biss.api.v1.csc.asset.Asset"></a>

### Asset
单条资产记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| name | [string](#string) |  |  |
| amount | [string](#string) |  | 总额 |
| available | [string](#string) |  | 可用 |
| frozen | [string](#string) |  | 冻结 |
| usd_value | [string](#string) |  | USD 估值 |






<a name="biss.api.v1.csc.asset.AssetsResp"></a>

### AssetsResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| btc_value | [string](#string) |  | BTC 估值 |
| values | [LegalValue](#biss.api.v1.csc.asset.LegalValue) | repeated | 法币估值列表 |
| assets | [Asset](#biss.api.v1.csc.asset.Asset) | repeated | 资产列表(当前只有USDT,后续会有其他的) |






<a name="biss.api.v1.csc.asset.LegalValue"></a>

### LegalValue



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| legal_currency | [biss.common.Currency](#biss.common.Currency) |  | 法币类型 |
| legal_value | [string](#string) |  | 法币估值 |






<a name="biss.api.v1.csc.asset.Position"></a>

### Position



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| name | [string](#string) |  | 标的友好名 |
| qty | [string](#string) |  | 持仓总数 |
| frozen | [string](#string) |  | 冻结 |
| current_price | [string](#string) |  | 现价 |
| avg_price | [string](#string) |  | 平均成本 |
| profit | [string](#string) |  | 盈亏 |
| usd_value | [string](#string) |  | USD估值 |






<a name="biss.api.v1.csc.asset.PositionListResp"></a>

### PositionListResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| positions | [Position](#biss.api.v1.csc.asset.Position) | repeated |  |






<a name="biss.api.v1.csc.asset.TransferHistoricalRecord"></a>

### TransferHistoricalRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| qty | [string](#string) |  |  |
| time | [uint64](#uint64) |  |  |
| direct | [TransferDirect](#biss.api.v1.csc.asset.TransferDirect) |  | 划转方向 |






<a name="biss.api.v1.csc.asset.TransferHistoryReq"></a>

### TransferHistoryReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 可以为空,为空时时当前用户的所有转入记录 |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |






<a name="biss.api.v1.csc.asset.TransferHistoryResp"></a>

### TransferHistoryResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| records | [TransferHistoricalRecord](#biss.api.v1.csc.asset.TransferHistoricalRecord) | repeated |  |






<a name="biss.api.v1.csc.asset.TransferReq"></a>

### TransferReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 转入/出币股的数字货币(v1.0只有USDT) |
| qty | [string](#string) |  | 数量 |





 


<a name="biss.api.v1.csc.asset.TransferDirect"></a>

### TransferDirect


| Name | Number | Description |
| ---- | ------ | ----------- |
| TD_NONE | 0 |  |
| TD_TO_CSC | 1 | 币币转到币股 |
| TD_FROM_CSC | 2 | 币股转到币币 |


 

 


<a name="biss.api.v1.csc.asset.Assets"></a>

### Assets


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Assets | [.biss.common.Empty](#biss.common.Empty) | [AssetsResp](#biss.api.v1.csc.asset.AssetsResp) | 资产列表(暂时只有USDT，后续可能会增加) |
| Trans2CSC | [TransferReq](#biss.api.v1.csc.asset.TransferReq) | [.biss.common.Empty](#biss.common.Empty) | 转入 |
| TransFromCSC | [TransferReq](#biss.api.v1.csc.asset.TransferReq) | [.biss.common.Empty](#biss.common.Empty) | 转出 |
| TransferHistory | [TransferHistoryReq](#biss.api.v1.csc.asset.TransferHistoryReq) | [TransferHistoryResp](#biss.api.v1.csc.asset.TransferHistoryResp) | 划转记录 |
| PositionList | [.biss.common.Empty](#biss.common.Empty) | [PositionListResp](#biss.api.v1.csc.asset.PositionListResp) | 持仓列表 |

 



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


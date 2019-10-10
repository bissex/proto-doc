# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/ams/audit.proto](#proto/ams/audit.proto)
    - [AssetInfo](#biss.ams.audit.AssetInfo)
    - [AssetList](#biss.ams.audit.AssetList)
    - [AssetRisk](#biss.ams.audit.AssetRisk)
    - [DepositRecord](#biss.ams.audit.DepositRecord)
    - [DepositRecordList](#biss.ams.audit.DepositRecordList)
    - [GetAssetReq](#biss.ams.audit.GetAssetReq)
    - [GetDepositRecordReq](#biss.ams.audit.GetDepositRecordReq)
    - [GetKYCListReq](#biss.ams.audit.GetKYCListReq)
    - [GetUserInfoReq](#biss.ams.audit.GetUserInfoReq)
    - [GetUserInfoResp](#biss.ams.audit.GetUserInfoResp)
    - [GetUserKYCInfoReq](#biss.ams.audit.GetUserKYCInfoReq)
    - [GetUserKYCInfoResp](#biss.ams.audit.GetUserKYCInfoResp)
    - [GetWithdrawListReq](#biss.ams.audit.GetWithdrawListReq)
    - [GetWithdrawRecordReq](#biss.ams.audit.GetWithdrawRecordReq)
    - [KYCInfo](#biss.ams.audit.KYCInfo)
    - [KYCList](#biss.ams.audit.KYCList)
    - [KYCPassReq](#biss.ams.audit.KYCPassReq)
    - [KYCRefuseReq](#biss.ams.audit.KYCRefuseReq)
    - [SymbolInfo](#biss.ams.audit.SymbolInfo)
    - [UnbindGAReq](#biss.ams.audit.UnbindGAReq)
    - [UnbindMobileReq](#biss.ams.audit.UnbindMobileReq)
    - [WithdrawBatchConfirmReq](#biss.ams.audit.WithdrawBatchConfirmReq)
    - [WithdrawConfirmReq](#biss.ams.audit.WithdrawConfirmReq)
    - [WithdrawInfo](#biss.ams.audit.WithdrawInfo)
    - [WithdrawList](#biss.ams.audit.WithdrawList)
    - [WithdrawOverview](#biss.ams.audit.WithdrawOverview)
    - [WithdrawRecord](#biss.ams.audit.WithdrawRecord)
    - [WithdrawRecordList](#biss.ams.audit.WithdrawRecordList)
    - [WithdrawResendReq](#biss.ams.audit.WithdrawResendReq)
  
    - [OperationRisk](#biss.ams.audit.OperationRisk)
    - [SystemRisk](#biss.ams.audit.SystemRisk)
  
  
    - [Audit](#biss.ams.audit.Audit)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/ams/audit.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/ams/audit.proto



<a name="biss.ams.audit.AssetInfo"></a>

### AssetInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| total | [string](#string) |  | 总资产 |
| frozen | [string](#string) |  | 冻结资产 |
| available | [string](#string) |  | 可用资产 |
| total_deposit | [string](#string) |  | 总充值资产 |
| total_withdraw | [string](#string) |  | 总提现资产 |






<a name="biss.ams.audit.AssetList"></a>

### AssetList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| assets | [AssetInfo](#biss.ams.audit.AssetInfo) | repeated |  |






<a name="biss.ams.audit.AssetRisk"></a>

### AssetRisk



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| system_risk | [SystemRisk](#biss.ams.audit.SystemRisk) |  |  |






<a name="biss.ams.audit.DepositRecord"></a>

### DepositRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| amount | [string](#string) |  | 数量 |
| tx_id | [string](#string) |  | tx |
| block_height | [string](#string) |  | 区块高度 |
| status | [biss.api.v1.asset.DepositStatus](#biss.api.v1.asset.DepositStatus) |  | 状态 |
| create_time | [uint64](#uint64) |  | 充值时间 |
| confirm_time | [uint64](#uint64) |  | 确认时间 |






<a name="biss.ams.audit.DepositRecordList"></a>

### DepositRecordList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| deposits | [DepositRecord](#biss.ams.audit.DepositRecord) | repeated |  |






<a name="biss.ams.audit.GetAssetReq"></a>

### GetAssetReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| uid | [uint64](#uint64) |  |  |






<a name="biss.ams.audit.GetDepositRecordReq"></a>

### GetDepositRecordReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| uid | [uint64](#uint64) |  |  |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |






<a name="biss.ams.audit.GetKYCListReq"></a>

### GetKYCListReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [biss.api.v1.account.KYCStatus](#biss.api.v1.account.KYCStatus) |  |  |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |






<a name="biss.ams.audit.GetUserInfoReq"></a>

### GetUserInfoReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| info | [string](#string) |  | email, uid |






<a name="biss.ams.audit.GetUserInfoResp"></a>

### GetUserInfoResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| uid | [uint64](#uint64) |  |  |
| email | [string](#string) |  |  |
| country | [string](#string) |  |  |
| mobile | [string](#string) |  |  |
| ga_ver | [string](#string) |  |  |
| name | [string](#string) |  |  |
| id_number | [string](#string) |  |  |






<a name="biss.ams.audit.GetUserKYCInfoReq"></a>

### GetUserKYCInfoReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  |  |






<a name="biss.ams.audit.GetUserKYCInfoResp"></a>

### GetUserKYCInfoResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| kycs | [KYCInfo](#biss.ams.audit.KYCInfo) | repeated |  |






<a name="biss.ams.audit.GetWithdrawListReq"></a>

### GetWithdrawListReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [biss.api.v1.asset.WithdrawStatus](#biss.api.v1.asset.WithdrawStatus) |  |  |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |






<a name="biss.ams.audit.GetWithdrawRecordReq"></a>

### GetWithdrawRecordReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| uid | [uint64](#uint64) |  |  |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |






<a name="biss.ams.audit.KYCInfo"></a>

### KYCInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint64](#uint64) |  |  |
| uid | [uint64](#uint64) |  |  |
| country | [string](#string) |  |  |
| name | [string](#string) |  |  |
| id_number | [string](#string) |  |  |
| urls | [string](#string) | repeated |  |
| submit_time | [uint64](#uint64) |  |  |
| status | [biss.api.v1.account.KYCStatus](#biss.api.v1.account.KYCStatus) |  |  |
| mesg | [string](#string) |  |  |
| auditor | [string](#string) |  |  |
| update_time | [uint64](#uint64) |  |  |






<a name="biss.ams.audit.KYCList"></a>

### KYCList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| kycs | [KYCInfo](#biss.ams.audit.KYCInfo) | repeated |  |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |






<a name="biss.ams.audit.KYCPassReq"></a>

### KYCPassReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint64](#uint64) |  |  |
| uid | [uint64](#uint64) |  |  |
| id_number | [string](#string) |  |  |






<a name="biss.ams.audit.KYCRefuseReq"></a>

### KYCRefuseReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint64](#uint64) |  |  |
| uid | [uint64](#uint64) |  |  |
| mesg | [string](#string) |  |  |
| auditor | [string](#string) |  |  |






<a name="biss.ams.audit.SymbolInfo"></a>

### SymbolInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| to_withdraw | [string](#string) |  |  |
| daily_withdraw | [string](#string) |  |  |
| balance | [string](#string) |  |  |






<a name="biss.ams.audit.UnbindGAReq"></a>

### UnbindGAReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| uid | [uint64](#uint64) |  |  |






<a name="biss.ams.audit.UnbindMobileReq"></a>

### UnbindMobileReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| uid | [uint64](#uint64) |  |  |






<a name="biss.ams.audit.WithdrawBatchConfirmReq"></a>

### WithdrawBatchConfirmReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| confirms | [WithdrawConfirmReq](#biss.ams.audit.WithdrawConfirmReq) | repeated |  |






<a name="biss.ams.audit.WithdrawConfirmReq"></a>

### WithdrawConfirmReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| wid | [uint64](#uint64) |  |  |
| symbol | [string](#string) |  |  |
| qty | [string](#string) |  |  |






<a name="biss.ams.audit.WithdrawInfo"></a>

### WithdrawInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| wid | [uint64](#uint64) |  |  |
| uid | [uint64](#uint64) |  |  |
| name | [string](#string) |  |  |
| symbol | [string](#string) |  |  |
| qty | [string](#string) |  |  |
| total | [string](#string) |  |  |
| create_time | [uint64](#uint64) |  |  |
| status | [biss.api.v1.asset.WithdrawStatus](#biss.api.v1.asset.WithdrawStatus) |  |  |
| tx_id | [string](#string) |  |  |
| confirm_time | [uint64](#uint64) |  |  |
| email | [string](#string) |  |  |
| address | [string](#string) |  |  |
| eos_memo | [string](#string) |  |  |
| operation_risk | [OperationRisk](#biss.ams.audit.OperationRisk) |  |  |
| explorer_url | [string](#string) |  |  |






<a name="biss.ams.audit.WithdrawList"></a>

### WithdrawList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| withdraws | [WithdrawInfo](#biss.ams.audit.WithdrawInfo) | repeated |  |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |






<a name="biss.ams.audit.WithdrawOverview"></a>

### WithdrawOverview



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbols | [SymbolInfo](#biss.ams.audit.SymbolInfo) | repeated |  |






<a name="biss.ams.audit.WithdrawRecord"></a>

### WithdrawRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| amount | [string](#string) |  | 数量 |
| block_height | [string](#string) |  | 区块高度 |
| status | [biss.api.v1.asset.WithdrawStatus](#biss.api.v1.asset.WithdrawStatus) |  | 状态 |
| create_time | [uint64](#uint64) |  | 提现时间 |
| confirm_time | [uint64](#uint64) |  | 确认时间 |






<a name="biss.ams.audit.WithdrawRecordList"></a>

### WithdrawRecordList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| withdraws | [WithdrawRecord](#biss.ams.audit.WithdrawRecord) | repeated |  |






<a name="biss.ams.audit.WithdrawResendReq"></a>

### WithdrawResendReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| wid | [uint64](#uint64) |  |  |





 


<a name="biss.ams.audit.OperationRisk"></a>

### OperationRisk


| Name | Number | Description |
| ---- | ------ | ----------- |
| OR_WHITE | 0 |  |
| OR_ORANGE | 1 |  |
| OR_RED | 2 |  |



<a name="biss.ams.audit.SystemRisk"></a>

### SystemRisk


| Name | Number | Description |
| ---- | ------ | ----------- |
| SR_WHITE | 0 |  |
| SR_BLACK | 1 |  |


 

 


<a name="biss.ams.audit.Audit"></a>

### Audit


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetWithdrawOverview | [.biss.common.Empty](#biss.common.Empty) | [WithdrawOverview](#biss.ams.audit.WithdrawOverview) | 提现每日概览 |
| GetWithdrawList | [GetWithdrawListReq](#biss.ams.audit.GetWithdrawListReq) | [WithdrawList](#biss.ams.audit.WithdrawList) | 获取提现列表 |
| WithdrawConfirm | [WithdrawConfirmReq](#biss.ams.audit.WithdrawConfirmReq) | [.biss.common.Empty](#biss.common.Empty) | 提现确认 |
| WithdrawBatchConfirm | [WithdrawBatchConfirmReq](#biss.ams.audit.WithdrawBatchConfirmReq) | [.biss.common.Empty](#biss.common.Empty) | 提现批量确认 |
| GetKYCList | [GetKYCListReq](#biss.ams.audit.GetKYCListReq) | [KYCList](#biss.ams.audit.KYCList) | KYC列表 |
| KYCPass | [KYCPassReq](#biss.ams.audit.KYCPassReq) | [.biss.common.Empty](#biss.common.Empty) | KYC审核通过 |
| KYCRefuse | [KYCRefuseReq](#biss.ams.audit.KYCRefuseReq) | [.biss.common.Empty](#biss.common.Empty) | KYC审核拒绝 |
| GetAsset | [GetAssetReq](#biss.ams.audit.GetAssetReq) | [AssetList](#biss.ams.audit.AssetList) | 用户资产 |
| GetDepositRecord | [GetDepositRecordReq](#biss.ams.audit.GetDepositRecordReq) | [DepositRecordList](#biss.ams.audit.DepositRecordList) | 用户充值记录 |
| GetWithdrawRecord | [GetWithdrawRecordReq](#biss.ams.audit.GetWithdrawRecordReq) | [WithdrawRecordList](#biss.ams.audit.WithdrawRecordList) | 用户提现记录 |
| GetUserInfoByEmail | [GetUserInfoReq](#biss.ams.audit.GetUserInfoReq) | [GetUserInfoResp](#biss.ams.audit.GetUserInfoResp) | 搜索用户信息 |
| UnbindMobile | [UnbindMobileReq](#biss.ams.audit.UnbindMobileReq) | [.biss.common.Empty](#biss.common.Empty) | 解绑用户手机号 |
| UnbindGA | [UnbindGAReq](#biss.ams.audit.UnbindGAReq) | [.biss.common.Empty](#biss.common.Empty) | 解绑用户GA |
| GetUserKYCInfoByEmail | [GetUserKYCInfoReq](#biss.ams.audit.GetUserKYCInfoReq) | [GetUserKYCInfoResp](#biss.ams.audit.GetUserKYCInfoResp) | 搜索用户KYC信息 |
| WithdrawResend | [WithdrawResendReq](#biss.ams.audit.WithdrawResendReq) | [.biss.common.Empty](#biss.common.Empty) | 提现重新上链 |
| SysAssetRisk | [.biss.common.Empty](#biss.common.Empty) | [AssetRisk](#biss.ams.audit.AssetRisk) | 系统资产风险 |

 



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


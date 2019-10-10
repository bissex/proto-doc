# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/activity/profit.proto](#proto/api/v1/activity/profit.proto)
    - [ConfirmReq](#biss.api.v1.activity.profit.ConfirmReq)
    - [GetCSCBookProfitResp](#biss.api.v1.activity.profit.GetCSCBookProfitResp)
    - [ProfitInfo](#biss.api.v1.activity.profit.ProfitInfo)
    - [ProfitList](#biss.api.v1.activity.profit.ProfitList)
    - [ProfitStatus](#biss.api.v1.activity.profit.ProfitStatus)
    - [TaskStatus](#biss.api.v1.activity.profit.TaskStatus)
  
    - [CSCBookStatus](#biss.api.v1.activity.profit.CSCBookStatus)
    - [ProfitStage](#biss.api.v1.activity.profit.ProfitStage)
    - [ReceiveStatus](#biss.api.v1.activity.profit.ReceiveStatus)
    - [TradeCondition](#biss.api.v1.activity.profit.TradeCondition)
  
  
    - [Profit](#biss.api.v1.activity.profit.Profit)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/activity/profit.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/activity/profit.proto



<a name="biss.api.v1.activity.profit.ConfirmReq"></a>

### ConfirmReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| nation_code | [string](#string) |  | 国家码 |
| mobile | [string](#string) |  | 手机号 |
| verify | [biss.api.v1.account.VerifyReq](#biss.api.v1.account.VerifyReq) |  | 验证码 |






<a name="biss.api.v1.activity.profit.GetCSCBookProfitResp"></a>

### GetCSCBookProfitResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [CSCBookStatus](#biss.api.v1.activity.profit.CSCBookStatus) |  |  |






<a name="biss.api.v1.activity.profit.ProfitInfo"></a>

### ProfitInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 股票名称 |
| bonus | [string](#string) |  | 奖励持仓 |
| market | [string](#string) |  | 市价 |
| aver_cost | [string](#string) |  | 平均成本 |
| profit | [string](#string) |  | 盈亏 |
| usdt_value | [string](#string) |  | USDT估值 |






<a name="biss.api.v1.activity.profit.ProfitList"></a>

### ProfitList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| profits | [ProfitInfo](#biss.api.v1.activity.profit.ProfitInfo) | repeated |  |






<a name="biss.api.v1.activity.profit.ProfitStatus"></a>

### ProfitStatus



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| stage | [ProfitStage](#biss.api.v1.activity.profit.ProfitStage) |  | 活动阶段 |
| count_down | [uint64](#uint64) |  | 倒计时 |






<a name="biss.api.v1.activity.profit.TaskStatus"></a>

### TaskStatus



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| trade_status | [TradeCondition](#biss.api.v1.activity.profit.TradeCondition) |  | 交易任务状态 |
| kyc_status | [biss.api.v1.account.KYCStatus](#biss.api.v1.account.KYCStatus) |  | kyc认证状态 |
| receive_status | [ReceiveStatus](#biss.api.v1.activity.profit.ReceiveStatus) |  | 领取权限 |





 


<a name="biss.api.v1.activity.profit.CSCBookStatus"></a>

### CSCBookStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| CS_BOOKED | 0 | 已预约 |
| CS_NOT_BOOKED | 1 | 未预约 |
| CS_NOT_VALID | 2 | 无效 |



<a name="biss.api.v1.activity.profit.ProfitStage"></a>

### ProfitStage


| Name | Number | Description |
| ---- | ------ | ----------- |
| PS_NOT_BEGIN | 0 | 未开始计算收益 |
| PS_BEGIN | 1 | 开始计算收益 |
| PS_END | 2 | 收益结算完成 |



<a name="biss.api.v1.activity.profit.ReceiveStatus"></a>

### ReceiveStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| RS_NONE | 0 |  |
| RS_TO_FINISH | 1 | 未完成 |
| RS_TO_RECEIVE | 2 | 已完成未领取 |
| RS_DONE | 3 | 已领取 |
| RS_NOT_BEGIN | 4 | 未开始 |



<a name="biss.api.v1.activity.profit.TradeCondition"></a>

### TradeCondition


| Name | Number | Description |
| ---- | ------ | ----------- |
| TC_TO_FINISH | 0 | 去完成 |
| TC_DONE | 1 | 已完成 |


 

 


<a name="biss.api.v1.activity.profit.Profit"></a>

### Profit


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetCSCBookProfit | [ConfirmReq](#biss.api.v1.activity.profit.ConfirmReq) | [GetCSCBookProfitResp](#biss.api.v1.activity.profit.GetCSCBookProfitResp) | 领取股票预约收益 |
| GetIOSTVoteProfit | [ConfirmReq](#biss.api.v1.activity.profit.ConfirmReq) | [.biss.common.Empty](#biss.common.Empty) | 领取IOST投票收益 |
| GetProfitStatus | [.biss.common.Empty](#biss.common.Empty) | [ProfitStatus](#biss.api.v1.activity.profit.ProfitStatus) | 活动状态 |
| GetProfitList | [.biss.common.Empty](#biss.common.Empty) | [ProfitList](#biss.api.v1.activity.profit.ProfitList) | 收益列表 |
| GetTaskStatus | [.biss.common.Empty](#biss.common.Empty) | [TaskStatus](#biss.api.v1.activity.profit.TaskStatus) | 任务完成情况 |
| GetReward | [.biss.common.Empty](#biss.common.Empty) | [.biss.common.Empty](#biss.common.Empty) | 奖励领取 |

 



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


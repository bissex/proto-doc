# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/vip.proto](#proto/api/v1/vip.proto)
    - [Asset](#biss.api.v1.vip.Asset)
    - [CommissionRecord](#biss.api.v1.vip.CommissionRecord)
    - [CommissionRecordItem](#biss.api.v1.vip.CommissionRecordItem)
    - [CommissionRecordReq](#biss.api.v1.vip.CommissionRecordReq)
    - [PaginationReq](#biss.api.v1.vip.PaginationReq)
    - [PaginationResp](#biss.api.v1.vip.PaginationResp)
    - [PositionInfo](#biss.api.v1.vip.PositionInfo)
    - [PositionRecordItem](#biss.api.v1.vip.PositionRecordItem)
    - [PurchaseVipCardReq](#biss.api.v1.vip.PurchaseVipCardReq)
    - [ReferralInfo](#biss.api.v1.vip.ReferralInfo)
    - [ReferralInfoItem](#biss.api.v1.vip.ReferralInfoItem)
    - [ReferralInfoReq](#biss.api.v1.vip.ReferralInfoReq)
    - [ReferralRecord](#biss.api.v1.vip.ReferralRecord)
    - [ReferralRecordItem](#biss.api.v1.vip.ReferralRecordItem)
    - [ReferralRecordReq](#biss.api.v1.vip.ReferralRecordReq)
    - [VipCardSalesStatus](#biss.api.v1.vip.VipCardSalesStatus)
    - [VipReward](#biss.api.v1.vip.VipReward)
  
  
  
    - [VipSvc](#biss.api.v1.vip.VipSvc)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/vip.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/vip.proto



<a name="biss.api.v1.vip.Asset"></a>

### Asset
资产


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| qty | [string](#string) |  | 数量 |






<a name="biss.api.v1.vip.CommissionRecord"></a>

### CommissionRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pagination | [PaginationResp](#biss.api.v1.vip.PaginationResp) |  | 分页信息 |
| items | [CommissionRecordItem](#biss.api.v1.vip.CommissionRecordItem) | repeated |  |






<a name="biss.api.v1.vip.CommissionRecordItem"></a>

### CommissionRecordItem
返佣记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  | 账号 |
| level | [biss.common.VipLevel](#biss.common.VipLevel) |  | 会员级别 |
| depth | [string](#string) |  | 邀请深度 |
| income | [Asset](#biss.api.v1.vip.Asset) | repeated | 返佣收入 |






<a name="biss.api.v1.vip.CommissionRecordReq"></a>

### CommissionRecordReq
返佣记录请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pagination | [PaginationReq](#biss.api.v1.vip.PaginationReq) |  | 分页信息 |






<a name="biss.api.v1.vip.PaginationReq"></a>

### PaginationReq
分页请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  | 页号（从1开始） |
| page_size | [uint32](#uint32) |  | 每页大小 |






<a name="biss.api.v1.vip.PaginationResp"></a>

### PaginationResp
分页应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  | 页号（从1开始） |
| page_size | [uint32](#uint32) |  | 每页大小 |
| page_count | [uint32](#uint32) |  | 总页数 |
| item_count | [uint32](#uint32) |  | 总条数 |






<a name="biss.api.v1.vip.PositionInfo"></a>

### PositionInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| average | [string](#string) |  | 平均持仓 |
| items | [PositionRecordItem](#biss.api.v1.vip.PositionRecordItem) | repeated | 持仓记录 |






<a name="biss.api.v1.vip.PositionRecordItem"></a>

### PositionRecordItem
持仓信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 时间(UTC timestamp in millisecond) |
| value | [string](#string) |  | 持仓 |






<a name="biss.api.v1.vip.PurchaseVipCardReq"></a>

### PurchaseVipCardReq
购买会员卡请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sales_id | [uint32](#uint32) |  | 销售标识 |






<a name="biss.api.v1.vip.ReferralInfo"></a>

### ReferralInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pagination | [PaginationResp](#biss.api.v1.vip.PaginationResp) |  | 分页信息 |
| items | [ReferralInfoItem](#biss.api.v1.vip.ReferralInfoItem) | repeated |  |






<a name="biss.api.v1.vip.ReferralInfoItem"></a>

### ReferralInfoItem
邀请信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  | 账号 |
| time | [uint64](#uint64) |  | 注册时间(UTC timestamp in millisecond) |
| level | [biss.common.VipLevel](#biss.common.VipLevel) |  | 会员级别 |
| depth | [string](#string) |  | 邀请深度 |






<a name="biss.api.v1.vip.ReferralInfoReq"></a>

### ReferralInfoReq
邀请信息请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pagination | [PaginationReq](#biss.api.v1.vip.PaginationReq) |  | 分页信息 |






<a name="biss.api.v1.vip.ReferralRecord"></a>

### ReferralRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pagination | [PaginationResp](#biss.api.v1.vip.PaginationResp) |  | 分页信息 |
| items | [ReferralRecordItem](#biss.api.v1.vip.ReferralRecordItem) | repeated |  |






<a name="biss.api.v1.vip.ReferralRecordItem"></a>

### ReferralRecordItem
邀请(奖励)记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  | 账号 |
| time | [uint64](#uint64) |  | 注册时间(UTC timestamp in millisecond) |
| level | [biss.common.VipLevel](#biss.common.VipLevel) |  | 会员级别 |
| depth | [string](#string) |  | 邀请深度 |
| reward | [Asset](#biss.api.v1.vip.Asset) |  | 邀请奖励 |






<a name="biss.api.v1.vip.ReferralRecordReq"></a>

### ReferralRecordReq
邀请(奖励)记录请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pagination | [PaginationReq](#biss.api.v1.vip.PaginationReq) |  | 分页信息 |






<a name="biss.api.v1.vip.VipCardSalesStatus"></a>

### VipCardSalesStatus
会员卡销售状态


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sales_id | [uint32](#uint32) |  | 销售标识 |
| symbol | [string](#string) |  | 标的 |
| original_price | [string](#string) |  | 原价 |
| current_price | [string](#string) |  | 现价 |
| discount | [string](#string) |  | 折扣(ENG:discount%off)(CHN:10-discount/10折) |
| next_level_step | [string](#string) |  | 下一级涨幅 |
| cur_level_total | [string](#string) |  | 当前级别总人数 |
| cur_level_left | [string](#string) |  | 当前级别剩余人数 |
| start_date | [uint64](#uint64) |  | 开始日期(UTC timestamp in millisecond)(仅年月日有效) |
| finish_date | [uint64](#uint64) |  | 结束日期(UTC timestamp in millisecond)(仅年月日有效) |
| total_sales | [string](#string) |  | 销售总人数 |






<a name="biss.api.v1.vip.VipReward"></a>

### VipReward
会员奖励


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| referral_total_num | [string](#string) |  | 邀请总人数(1级) |
| referral_vip_num | [string](#string) |  | 邀请会员人数(1级) |
| referral_reward | [Asset](#biss.api.v1.vip.Asset) |  | 邀请奖励 |
| commission_income | [Asset](#biss.api.v1.vip.Asset) | repeated | 返佣收入 |
| referral_total_num_l2 | [string](#string) |  | 邀请总人数(2级) |
| referral_vip_num_l2 | [string](#string) |  | 邀请会员人数(2级) |
| referral_reward_max | [Asset](#biss.api.v1.vip.Asset) |  | 邀请奖励(最大值) |





 

 

 


<a name="biss.api.v1.vip.VipSvc"></a>

### VipSvc


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetVipCardSalesStatus | [.biss.common.Empty](#biss.common.Empty) | [VipCardSalesStatus](#biss.api.v1.vip.VipCardSalesStatus) | 获取会员卡销售状态 |
| PurchaseVipCard | [PurchaseVipCardReq](#biss.api.v1.vip.PurchaseVipCardReq) | [.biss.common.Empty](#biss.common.Empty) | 购买会员卡 |
| GetVipReward | [.biss.common.Empty](#biss.common.Empty) | [VipReward](#biss.api.v1.vip.VipReward) | 会员奖励 |
| GetReferralRecord | [ReferralRecordReq](#biss.api.v1.vip.ReferralRecordReq) | [ReferralRecord](#biss.api.v1.vip.ReferralRecord) | 邀请(奖励)记录 |
| GetCommissionRecord | [CommissionRecordReq](#biss.api.v1.vip.CommissionRecordReq) | [CommissionRecord](#biss.api.v1.vip.CommissionRecord) | 返佣记录 |
| GetReferralInfo | [ReferralInfoReq](#biss.api.v1.vip.ReferralInfoReq) | [ReferralInfo](#biss.api.v1.vip.ReferralInfo) | 邀请信息 |
| GetPositionInfo | [.biss.common.Empty](#biss.common.Empty) | [PositionInfo](#biss.api.v1.vip.PositionInfo) | 持仓信息 |

 



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


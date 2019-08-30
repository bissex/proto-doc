



# biss.api.v1.asset.Assets



## Assets

资产列表
    
> `GRPC` Assets([.biss.common.Empty](#.biss.common.Empty)) return [AssetsResp](#AssetsResp)






> `HTTP` `GET` /v1/assets/assets
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## TickerAsset

资产列表
    
> `GRPC` TickerAsset([.biss.common.trade.Ticker](#.biss.common.trade.Ticker)) return [TickerAssetResp](#TickerAssetResp)


 <!-- end with -->

## Deposit

充值信息
    
> `GRPC` Deposit([DepositReq](#DepositReq)) return [DepositResp](#DepositResp)


 <!-- end with -->

## DepositHistory

充值记录
    
> `GRPC` DepositHistory([DepositHistoryReq](#DepositHistoryReq)) return [DepositHistoryResp](#DepositHistoryResp)


 <!-- end with -->

## WithdrawCalculate

提现计算
    
> `GRPC` WithdrawCalculate([WithdrawCalculateReq](#WithdrawCalculateReq)) return [WithdrawCalculateResp](#WithdrawCalculateResp)


 <!-- end with -->

## Withdraw

提现
    
> `GRPC` Withdraw([WithdrawReq](#WithdrawReq)) return [WithdrawResp](#WithdrawResp)


 <!-- end with -->

## WithdrawHistory

提现记录
    
> `GRPC` WithdrawHistory([WithdrawHistoryReq](#WithdrawHistoryReq)) return [WithdrawHistoryResp](#WithdrawHistoryResp)


 <!-- end with -->

## CancelWithdraw

取消提现
    
> `GRPC` CancelWithdraw([CancelWithdrawReq](#CancelWithdrawReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## AddWithdrawAddress

添加提现地址
    
> `GRPC` AddWithdrawAddress([AddWithdrawAddressReq](#AddWithdrawAddressReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## DeleteWithdrawAddress

删除提现地址
    
> `GRPC` DeleteWithdrawAddress([DeleteWithdrawAddressReq](#DeleteWithdrawAddressReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## WithdrawAddresses

提现地址列表
    
> `GRPC` WithdrawAddresses([WithdrawAddressesReq](#WithdrawAddressesReq)) return [WithdrawAddressesResp](#WithdrawAddressesResp)


 <!-- end with -->

## GetSymbolList

获取支持的币种
    
> `GRPC` GetSymbolList([.biss.common.Empty](#.biss.common.Empty)) return [.biss.api.v1.system.SymbolList](#.biss.api.v1.system.SymbolList)


 <!-- end with -->

## GetTickerList

获取支持的币种
    
> `GRPC` GetTickerList([.biss.common.Empty](#.biss.common.Empty)) return [.biss.api.v1.system.TickerList](#.biss.api.v1.system.TickerList)


 <!-- end with -->

## RewardHistory

获取奖励历史
    
> `GRPC` RewardHistory([RewardHistoryReq](#RewardHistoryReq)) return [RewardHistoryResp](#RewardHistoryResp)


 <!-- end with -->

 <!-- end methods -->
 <!-- end services -->


# 数据对象



## AddWithdrawAddressReq

添加提币地址


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| address | [Address](#Address) |  | 地址 |




## Address

提币地址


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| label | [string](#string) |  | 备注 |
| address | [string](#string) |  | 地址 |
| eos_memo | [string](#string) |  | EOS 专用地址标签 |




## Asset

单条资产记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| name | [string](#string) |  | 名称 |
| amount | [string](#string) |  | 总额 |
| available | [string](#string) |  | 可用 |
| frozen | [string](#string) |  | 冻结 |
| btc_value | [string](#string) |  | BTC 估值 |
| withdraw_enable | [bool](#bool) |  | 允许提现 |
| deposit_enable | [bool](#bool) |  | 允许充值 |




## AssetsResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| btc_value | [string](#string) |  | BTC 估值 |
| values | [LegalValue](#LegalValue) | repeated | 法币估值列表 |
| assets | [Asset](#Asset) | repeated | 资产列表 |




## CancelWithdrawReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| withdraw_id | [uint32](#uint32) |  | 提币ID,用于唯一确认一个提币请求 |




## DeleteWithdrawAddressReq

删除提币地址


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| address | [string](#string) |  | 地址 |
| eos_memo | [string](#string) |  | EOS 专用地址标签 |




## DepositHistoricalRecord




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 充值时间, UTC timestamp in micro second |
| symbol | [string](#string) |  | 充值标的 |
| qty | [string](#string) |  | 充值数量 |
| status | [DepositStatus](#DepositStatus) |  | 充值状态 |
| tx_id | [string](#string) |  | 网络交易ID |
| tx_time | [uint64](#uint64) |  | 交易确认时间, UTC timestamp in micro second |
| status_schedule | [uint32](#uint32) |  | 确认的区块进度,在充值状态中显示 |
| status_confirm | [uint32](#uint32) |  | 确认区块总数，在充值状态中显示 |
| explorer_url | [string](#string) |  | Txid Explorer URL |




## DepositHistoryReq

symbol 可选，symbol 不存在则返回全部历史


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |




## DepositHistoryResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| records | [DepositHistoricalRecord](#DepositHistoricalRecord) | repeated |  |




## DepositReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |




## DepositResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| address | [string](#string) |  | 地址 |
| eos_memo | [string](#string) |  | EOS地址专用标签 |
| qr | [bytes](#bytes) |  | 二维码 JPG |
| confirm_blocks | [uint32](#uint32) |  | 确认区块数量 |
| withdraw_blocks | [uint32](#uint32) |  | 可用区块数量 |
| min_qty | [string](#string) |  | 最小充值数量 |




## LegalValue




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| legal_currency | [biss.common.Currency](#biss.common.Currency) |  | 法币类型 |
| legal_value | [string](#string) |  | 法币估值 |




## Reward

活动奖励记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 奖励时间 |
| symbol | [string](#string) |  | 币种 |
| type | [string](#string) |  | 活动类型 |
| qty | [string](#string) |  | 数量 |
| status | [RewardStatus](#RewardStatus) |  | 状态 |
| description | [string](#string) |  | 说明 |




## RewardHistoryReq

活动奖励历史请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |




## RewardHistoryResp

活动奖励历史


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| rewards | [Reward](#Reward) | repeated | 活动 |




## TickerAssetResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| symbol_available | [string](#string) |  | symbol可用余额 |
| market_available | [string](#string) |  | market可用余额 |




## WithdrawAddressesReq

提币地址列表
symbol 可选，symbol 不存在则返回全部标的的提币地址


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |




## WithdrawAddressesResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| addresses | [Address](#Address) | repeated |  |




## WithdrawCalculateReq

计算提币数据
qty 为可选数据，不提供 qty 则 WithdrawCalculateResp 不返回 actual_qty 字段


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| qty | [string](#string) |  | 提币数量 |




## WithdrawCalculateResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| balance | [string](#string) |  | 余额 |
| global_quota | [string](#string) |  | 全局提币额度 |
| global_withdraw_qty | [string](#string) |  | 全局已使用提币数量 |
| current_quota | [string](#string) |  | 本币提币额度 |
| current_withdraw_qty | [string](#string) |  | 本币已使用提币数量 |
| min_qty | [string](#string) |  | 最小提币数量 |
| fees | [string](#string) |  | 手续费(现价) |
| actual_qty | [string](#string) |  | 实际到账数量 |
| original_fees | [string](#string) |  | 手续费(原价) |
| fees_discount | [uint32](#uint32) |  | 提现手续费折扣百分比 * 100(中文:"[discount/10]折", 英文:"(100-[discount])% off") |




## WithdrawHistoricalRecord




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 提币时间, UTC timestamp in micro second |
| symbol | [string](#string) |  | 标的 |
| qty | [string](#string) |  | 数量 |
| status | [WithdrawStatus](#WithdrawStatus) |  | 状态 |
| to | [string](#string) |  | 转出地址 |
| eos_memo | [string](#string) |  | EOS专用地址标签 |
| tx_id | [string](#string) |  | 网络交易ID |
| tx_time | [uint64](#uint64) |  | 网络确认时间, UTC timestamp in micro second |
| withdraw_id | [uint32](#uint32) |  | 数据中withdraw表中的唯一ID,可用于唯一确认一个提币请求 |
| explorer_url | [string](#string) |  | Txid Explorer URL |




## WithdrawHistoryReq

symbol 可选，symbol 不存在则返回全部历史


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |




## WithdrawHistoryResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| records | [WithdrawHistoricalRecord](#WithdrawHistoricalRecord) | repeated |  |




## WithdrawReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| address | [string](#string) |  | 提币地址 |
| eos_memo | [string](#string) |  | EOS专用地址标签 |
| qty | [string](#string) |  | 提币数量 |
| verifies | [biss.api.v1.account.Verifies](#biss.api.v1.account.Verifies) |  | SMS、email、GA验证码 |




## WithdrawResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tfa | [biss.api.v1.account.VerifyType](#biss.api.v1.account.VerifyType) | repeated | 需要三部验证类型 |


 <!-- end messages -->

# 枚举类型


<a name="biss.api.v1.asset.DepositStatus"></a>

## DepositStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| DS_NONE | 0 |  |
| DS_CONFIRMING | 1 | 确认中(不可撤销） |
| DS_DONE | 2 | 已完成 |



<a name="biss.api.v1.asset.RewardStatus"></a>

## RewardStatus
奖励状态

| Name | Number | Description |
| ---- | ------ | ----------- |
| RS_NONE | 0 |  |
| RS_COMFIRIMG | 1 | 确认中 |
| RS_DONE | 2 | 已完成 |



<a name="biss.api.v1.asset.WithdrawStatus"></a>

## WithdrawStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| WS_NONE | 0 |  |
| WS_SUBMITED | 1 | 已提交 (此状态可以撤销） |
| WS_CONFIRMING | 2 | 确认中 (该状态之后就不能在撤销） |
| WS_DONE | 3 | 已完成 |
| WS_CANCELED | 4 | 已撤销 |
| WS_APPROVED | 5 | 审核通过 (运营点击确认后) |


 <!-- end enums -->




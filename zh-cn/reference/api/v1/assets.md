# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/assets.proto](#proto/api/v1/assets.proto)
    - [AddWithdrawAddressReq](#biss.api.v1.asset.AddWithdrawAddressReq)
    - [Address](#biss.api.v1.asset.Address)
    - [Asset](#biss.api.v1.asset.Asset)
    - [AssetsContract](#biss.api.v1.asset.AssetsContract)
    - [AssetsItem](#biss.api.v1.asset.AssetsItem)
    - [AssetsRecord](#biss.api.v1.asset.AssetsRecord)
    - [AssetsRecordFilter](#biss.api.v1.asset.AssetsRecordFilter)
    - [AssetsRecordItem](#biss.api.v1.asset.AssetsRecordItem)
    - [AssetsRecordReq](#biss.api.v1.asset.AssetsRecordReq)
    - [AssetsReq](#biss.api.v1.asset.AssetsReq)
    - [AssetsResp](#biss.api.v1.asset.AssetsResp)
    - [CancelWithdrawReq](#biss.api.v1.asset.CancelWithdrawReq)
    - [DeleteWithdrawAddressReq](#biss.api.v1.asset.DeleteWithdrawAddressReq)
    - [DepositHistoricalRecord](#biss.api.v1.asset.DepositHistoricalRecord)
    - [DepositHistoryReq](#biss.api.v1.asset.DepositHistoryReq)
    - [DepositHistoryResp](#biss.api.v1.asset.DepositHistoryResp)
    - [DepositReq](#biss.api.v1.asset.DepositReq)
    - [DepositResp](#biss.api.v1.asset.DepositResp)
    - [LegalValue](#biss.api.v1.asset.LegalValue)
    - [Reward](#biss.api.v1.asset.Reward)
    - [RewardHistoryReq](#biss.api.v1.asset.RewardHistoryReq)
    - [RewardHistoryResp](#biss.api.v1.asset.RewardHistoryResp)
    - [RiskLimitList](#biss.api.v1.asset.RiskLimitList)
    - [RiskLimitListItem](#biss.api.v1.asset.RiskLimitListItem)
    - [RiskLimitListReq](#biss.api.v1.asset.RiskLimitListReq)
    - [RiskLimitReq](#biss.api.v1.asset.RiskLimitReq)
    - [TickerAssetResp](#biss.api.v1.asset.TickerAssetResp)
    - [TransferReq](#biss.api.v1.asset.TransferReq)
    - [WithdrawAddressesReq](#biss.api.v1.asset.WithdrawAddressesReq)
    - [WithdrawAddressesResp](#biss.api.v1.asset.WithdrawAddressesResp)
    - [WithdrawCalculateReq](#biss.api.v1.asset.WithdrawCalculateReq)
    - [WithdrawCalculateResp](#biss.api.v1.asset.WithdrawCalculateResp)
    - [WithdrawHistoricalRecord](#biss.api.v1.asset.WithdrawHistoricalRecord)
    - [WithdrawHistoryReq](#biss.api.v1.asset.WithdrawHistoryReq)
    - [WithdrawHistoryResp](#biss.api.v1.asset.WithdrawHistoryResp)
    - [WithdrawReq](#biss.api.v1.asset.WithdrawReq)
    - [WithdrawResp](#biss.api.v1.asset.WithdrawResp)
  
    - [AssetsRecordType](#biss.api.v1.asset.AssetsRecordType)
    - [DepositStatus](#biss.api.v1.asset.DepositStatus)
    - [RewardStatus](#biss.api.v1.asset.RewardStatus)
    - [WithdrawStatus](#biss.api.v1.asset.WithdrawStatus)
  
  
    - [Assets](#biss.api.v1.asset.Assets)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/assets.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/assets.proto



<a name="biss.api.v1.asset.AddWithdrawAddressReq"></a>

### AddWithdrawAddressReq
添加提币地址


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| address | [Address](#biss.api.v1.asset.Address) |  | 地址 |






<a name="biss.api.v1.asset.Address"></a>

### Address
提币地址


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| label | [string](#string) |  | 备注 |
| address | [string](#string) |  | 地址 |
| eos_memo | [string](#string) |  | EOS 专用地址标签 |






<a name="biss.api.v1.asset.Asset"></a>

### Asset
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






<a name="biss.api.v1.asset.AssetsContract"></a>

### AssetsContract
合约资产


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| total_balance | [AssetsItem](#biss.api.v1.asset.AssetsItem) |  | 总额 |
| available_margin | [AssetsItem](#biss.api.v1.asset.AssetsItem) |  | 可用保证金 |
| used_margin | [AssetsItem](#biss.api.v1.asset.AssetsItem) |  | 已用保证金 |
| unrealized_pnl | [AssetsItem](#biss.api.v1.asset.AssetsItem) |  | 未实现盈亏 |
| risk_limit_id | [uint32](#uint32) |  | 风险限额id |
| risk_limit | [string](#string) |  | 风险限额 |






<a name="biss.api.v1.asset.AssetsItem"></a>

### AssetsItem



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| qty | [string](#string) |  | 数量 |
| legal | [LegalValue](#biss.api.v1.asset.LegalValue) |  | 法币估值 |






<a name="biss.api.v1.asset.AssetsRecord"></a>

### AssetsRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pagination | [biss.common.PaginationResp](#biss.common.PaginationResp) |  | 分页信息 |
| items | [AssetsRecordItem](#biss.api.v1.asset.AssetsRecordItem) | repeated |  |






<a name="biss.api.v1.asset.AssetsRecordFilter"></a>

### AssetsRecordFilter



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| type | [AssetsRecordType](#biss.api.v1.asset.AssetsRecordType) |  | 类型 |






<a name="biss.api.v1.asset.AssetsRecordItem"></a>

### AssetsRecordItem
资产记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| type | [AssetsRecordType](#biss.api.v1.asset.AssetsRecordType) |  | 类型 |
| qty | [string](#string) |  | 数量 |
| time | [uint64](#uint64) |  | 时间(UTC timestamp in millisecond) |
| from | [biss.common.AccountType](#biss.common.AccountType) |  | 转出 |
| to | [biss.common.AccountType](#biss.common.AccountType) |  | 转入 |






<a name="biss.api.v1.asset.AssetsRecordReq"></a>

### AssetsRecordReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| pagination | [biss.common.PaginationReq](#biss.common.PaginationReq) |  | 分页信息 |
| filter | [AssetsRecordFilter](#biss.api.v1.asset.AssetsRecordFilter) |  | 筛选信息 |
| account | [biss.common.AccountType](#biss.common.AccountType) |  | 账户 |






<a name="biss.api.v1.asset.AssetsReq"></a>

### AssetsReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [biss.common.AccountType](#biss.common.AccountType) |  | 账户类型 |






<a name="biss.api.v1.asset.AssetsResp"></a>

### AssetsResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| btc_value | [string](#string) |  | BTC 估值 |
| values | [LegalValue](#biss.api.v1.asset.LegalValue) | repeated | 法币估值列表 |
| assets | [Asset](#biss.api.v1.asset.Asset) | repeated | 资产列表 |
| contract | [AssetsContract](#biss.api.v1.asset.AssetsContract) | repeated | 合约资产 |






<a name="biss.api.v1.asset.CancelWithdrawReq"></a>

### CancelWithdrawReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| withdraw_id | [uint32](#uint32) |  | 提币ID,用于唯一确认一个提币请求 |






<a name="biss.api.v1.asset.DeleteWithdrawAddressReq"></a>

### DeleteWithdrawAddressReq
删除提币地址


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| address | [string](#string) |  | 地址 |
| eos_memo | [string](#string) |  | EOS 专用地址标签 |






<a name="biss.api.v1.asset.DepositHistoricalRecord"></a>

### DepositHistoricalRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 充值时间, UTC timestamp in micro second |
| symbol | [string](#string) |  | 充值标的 |
| qty | [string](#string) |  | 充值数量 |
| status | [DepositStatus](#biss.api.v1.asset.DepositStatus) |  | 充值状态 |
| tx_id | [string](#string) |  | 网络交易ID |
| tx_time | [uint64](#uint64) |  | 交易确认时间, UTC timestamp in micro second |
| status_schedule | [uint32](#uint32) |  | 确认的区块进度,在充值状态中显示 |
| status_confirm | [uint32](#uint32) |  | 确认区块总数，在充值状态中显示 |
| explorer_url | [string](#string) |  | Txid Explorer URL |






<a name="biss.api.v1.asset.DepositHistoryReq"></a>

### DepositHistoryReq
symbol 可选，symbol 不存在则返回全部历史


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |






<a name="biss.api.v1.asset.DepositHistoryResp"></a>

### DepositHistoryResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| records | [DepositHistoricalRecord](#biss.api.v1.asset.DepositHistoricalRecord) | repeated |  |






<a name="biss.api.v1.asset.DepositReq"></a>

### DepositReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |






<a name="biss.api.v1.asset.DepositResp"></a>

### DepositResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| address | [string](#string) |  | 地址 |
| eos_memo | [string](#string) |  | EOS地址专用标签 |
| qr | [bytes](#bytes) |  | 二维码 JPG |
| confirm_blocks | [uint32](#uint32) |  | 确认区块数量 |
| withdraw_blocks | [uint32](#uint32) |  | 可用区块数量 |
| min_qty | [string](#string) |  | 最小充值数量 |






<a name="biss.api.v1.asset.LegalValue"></a>

### LegalValue



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| legal_currency | [biss.common.Currency](#biss.common.Currency) |  | 法币类型 |
| legal_value | [string](#string) |  | 法币估值 |






<a name="biss.api.v1.asset.Reward"></a>

### Reward
活动奖励记录


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 奖励时间 |
| symbol | [string](#string) |  | 币种 |
| type | [string](#string) |  | 活动类型 |
| qty | [string](#string) |  | 数量 |
| status | [RewardStatus](#biss.api.v1.asset.RewardStatus) |  | 状态 |
| description | [string](#string) |  | 说明 |






<a name="biss.api.v1.asset.RewardHistoryReq"></a>

### RewardHistoryReq
活动奖励历史请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |






<a name="biss.api.v1.asset.RewardHistoryResp"></a>

### RewardHistoryResp
活动奖励历史


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| rewards | [Reward](#biss.api.v1.asset.Reward) | repeated | 活动 |






<a name="biss.api.v1.asset.RiskLimitList"></a>

### RiskLimitList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| items | [RiskLimitListItem](#biss.api.v1.asset.RiskLimitListItem) | repeated |  |






<a name="biss.api.v1.asset.RiskLimitListItem"></a>

### RiskLimitListItem
风险限额列表


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| risk_limit_id | [uint32](#uint32) |  | 风险限额id |
| risk_limit | [string](#string) |  | 限额 |
| maintenance_margin_pct | [string](#string) |  | 维持保证金率 |
| initial_margin_pct | [string](#string) |  | 初始保证金率 |
| max_leverage | [string](#string) |  | 最大杠杆 |
| leverage_list | [string](#string) | repeated | 杠杆列表 |






<a name="biss.api.v1.asset.RiskLimitListReq"></a>

### RiskLimitListReq
风险限额列表请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |






<a name="biss.api.v1.asset.RiskLimitReq"></a>

### RiskLimitReq
风险限额请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| risk_limit_id | [uint32](#uint32) |  | 风险限额id |






<a name="biss.api.v1.asset.TickerAssetResp"></a>

### TickerAssetResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| symbol_available | [string](#string) |  | symbol可用余额 |
| market_available | [string](#string) |  | market可用余额 |






<a name="biss.api.v1.asset.TransferReq"></a>

### TransferReq
资产账户划转请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| from | [biss.common.AccountType](#biss.common.AccountType) |  | 转出账户 |
| to | [biss.common.AccountType](#biss.common.AccountType) |  | 转入账户 |
| symbol | [string](#string) |  | 资产类型 |
| qty | [string](#string) |  | 数量 |






<a name="biss.api.v1.asset.WithdrawAddressesReq"></a>

### WithdrawAddressesReq
提币地址列表
symbol 可选，symbol 不存在则返回全部标的的提币地址


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |






<a name="biss.api.v1.asset.WithdrawAddressesResp"></a>

### WithdrawAddressesResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| addresses | [Address](#biss.api.v1.asset.Address) | repeated |  |






<a name="biss.api.v1.asset.WithdrawCalculateReq"></a>

### WithdrawCalculateReq
计算提币数据
qty 为可选数据，不提供 qty 则 WithdrawCalculateResp 不返回 actual_qty 字段


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| qty | [string](#string) |  | 提币数量 |






<a name="biss.api.v1.asset.WithdrawCalculateResp"></a>

### WithdrawCalculateResp



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
| fees_discount | [uint32](#uint32) |  | 提现手续费折扣百分比 * 100(中文:&#34;[discount/10]折&#34;, 英文:&#34;(100-[discount])% off&#34;) |






<a name="biss.api.v1.asset.WithdrawHistoricalRecord"></a>

### WithdrawHistoricalRecord



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | 提币时间, UTC timestamp in micro second |
| symbol | [string](#string) |  | 标的 |
| qty | [string](#string) |  | 数量 |
| status | [WithdrawStatus](#biss.api.v1.asset.WithdrawStatus) |  | 状态 |
| to | [string](#string) |  | 转出地址 |
| eos_memo | [string](#string) |  | EOS专用地址标签 |
| tx_id | [string](#string) |  | 网络交易ID |
| tx_time | [uint64](#uint64) |  | 网络确认时间, UTC timestamp in micro second |
| withdraw_id | [uint32](#uint32) |  | 数据中withdraw表中的唯一ID,可用于唯一确认一个提币请求 |
| explorer_url | [string](#string) |  | Txid Explorer URL |






<a name="biss.api.v1.asset.WithdrawHistoryReq"></a>

### WithdrawHistoryReq
symbol 可选，symbol 不存在则返回全部历史


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |






<a name="biss.api.v1.asset.WithdrawHistoryResp"></a>

### WithdrawHistoryResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| records | [WithdrawHistoricalRecord](#biss.api.v1.asset.WithdrawHistoricalRecord) | repeated |  |






<a name="biss.api.v1.asset.WithdrawReq"></a>

### WithdrawReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 标的 |
| address | [string](#string) |  | 提币地址 |
| eos_memo | [string](#string) |  | EOS专用地址标签 |
| qty | [string](#string) |  | 提币数量 |
| verifies | [biss.api.v1.account.Verifies](#biss.api.v1.account.Verifies) |  | SMS、email、GA验证码 |






<a name="biss.api.v1.asset.WithdrawResp"></a>

### WithdrawResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tfa | [biss.api.v1.account.VerifyType](#biss.api.v1.account.VerifyType) | repeated | 需要三部验证类型 |





 


<a name="biss.api.v1.asset.AssetsRecordType"></a>

### AssetsRecordType
资产记录请求

| Name | Number | Description |
| ---- | ------ | ----------- |
| ART_NONE | 0 |  |
| ART_TRANSFER | 1 | 划转 |



<a name="biss.api.v1.asset.DepositStatus"></a>

### DepositStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| DS_NONE | 0 |  |
| DS_CONFIRMING | 1 | 确认中(不可撤销） |
| DS_DONE | 2 | 已完成 |



<a name="biss.api.v1.asset.RewardStatus"></a>

### RewardStatus
奖励状态

| Name | Number | Description |
| ---- | ------ | ----------- |
| RS_NONE | 0 |  |
| RS_COMFIRIMG | 1 | 确认中 |
| RS_DONE | 2 | 已完成 |



<a name="biss.api.v1.asset.WithdrawStatus"></a>

### WithdrawStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| WS_NONE | 0 |  |
| WS_SUBMITED | 1 | 已提交 (此状态可以撤销） |
| WS_CONFIRMING | 2 | 确认中 (该状态之后就不能在撤销） |
| WS_DONE | 3 | 已完成 |
| WS_CANCELED | 4 | 已撤销 |
| WS_APPROVED | 5 | 审核通过 (运营点击确认后) |


 

 


<a name="biss.api.v1.asset.Assets"></a>

### Assets


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Assets | [AssetsReq](#biss.api.v1.asset.AssetsReq) | [AssetsResp](#biss.api.v1.asset.AssetsResp) | 资产列表 |
| TickerAsset | [.biss.common.trade.Ticker](#biss.common.trade.Ticker) | [TickerAssetResp](#biss.api.v1.asset.TickerAssetResp) | 资产列表 |
| Deposit | [DepositReq](#biss.api.v1.asset.DepositReq) | [DepositResp](#biss.api.v1.asset.DepositResp) | 充值信息 |
| DepositHistory | [DepositHistoryReq](#biss.api.v1.asset.DepositHistoryReq) | [DepositHistoryResp](#biss.api.v1.asset.DepositHistoryResp) | 充值记录 |
| WithdrawCalculate | [WithdrawCalculateReq](#biss.api.v1.asset.WithdrawCalculateReq) | [WithdrawCalculateResp](#biss.api.v1.asset.WithdrawCalculateResp) | 提现计算 |
| Withdraw | [WithdrawReq](#biss.api.v1.asset.WithdrawReq) | [WithdrawResp](#biss.api.v1.asset.WithdrawResp) | 提现 |
| WithdrawHistory | [WithdrawHistoryReq](#biss.api.v1.asset.WithdrawHistoryReq) | [WithdrawHistoryResp](#biss.api.v1.asset.WithdrawHistoryResp) | 提现记录 |
| CancelWithdraw | [CancelWithdrawReq](#biss.api.v1.asset.CancelWithdrawReq) | [.biss.common.Empty](#biss.common.Empty) | 取消提现 |
| AddWithdrawAddress | [AddWithdrawAddressReq](#biss.api.v1.asset.AddWithdrawAddressReq) | [.biss.common.Empty](#biss.common.Empty) | 添加提现地址 |
| DeleteWithdrawAddress | [DeleteWithdrawAddressReq](#biss.api.v1.asset.DeleteWithdrawAddressReq) | [.biss.common.Empty](#biss.common.Empty) | 删除提现地址 |
| WithdrawAddresses | [WithdrawAddressesReq](#biss.api.v1.asset.WithdrawAddressesReq) | [WithdrawAddressesResp](#biss.api.v1.asset.WithdrawAddressesResp) | 提现地址列表 |
| GetSymbolList | [.biss.common.Empty](#biss.common.Empty) | [.biss.api.v1.system.SymbolList](#biss.api.v1.system.SymbolList) | 获取支持的币种 |
| GetTickerList | [.biss.common.Empty](#biss.common.Empty) | [.biss.api.v1.system.TickerList](#biss.api.v1.system.TickerList) | 获取支持的币种 |
| RewardHistory | [RewardHistoryReq](#biss.api.v1.asset.RewardHistoryReq) | [RewardHistoryResp](#biss.api.v1.asset.RewardHistoryResp) | 获取奖励历史 |
| Transfer | [TransferReq](#biss.api.v1.asset.TransferReq) | [.biss.common.Empty](#biss.common.Empty) | 资产账户划转 |
| GetAssetsRecord | [AssetsRecordReq](#biss.api.v1.asset.AssetsRecordReq) | [AssetsRecord](#biss.api.v1.asset.AssetsRecord) | 获取资产记录 |
| GetRiskLimitList | [RiskLimitListReq](#biss.api.v1.asset.RiskLimitListReq) | [RiskLimitList](#biss.api.v1.asset.RiskLimitList) | 获取风险限额列表 |
| SetRiskLimit | [RiskLimitReq](#biss.api.v1.asset.RiskLimitReq) | [.biss.common.Empty](#biss.common.Empty) | 设置风险限额 |

 



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


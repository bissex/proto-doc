# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/system.proto](#proto/api/v1/system.proto)
    - [AnnouncementInfo](#biss.api.v1.system.AnnouncementInfo)
    - [AppVersion](#biss.api.v1.system.AppVersion)
    - [AppVersionResp](#biss.api.v1.system.AppVersionResp)
    - [AppVersionResp.VersionsEntry](#biss.api.v1.system.AppVersionResp.VersionsEntry)
    - [BannerConfig](#biss.api.v1.system.BannerConfig)
    - [BannerConfig.HeroBannerConfig](#biss.api.v1.system.BannerConfig.HeroBannerConfig)
    - [CSCMarketInfo](#biss.api.v1.system.CSCMarketInfo)
    - [CSCMarketList](#biss.api.v1.system.CSCMarketList)
    - [CSCSymbolInfo](#biss.api.v1.system.CSCSymbolInfo)
    - [CSCSymbolInfo.IntrosEntry](#biss.api.v1.system.CSCSymbolInfo.IntrosEntry)
    - [CSCSymbolIntro](#biss.api.v1.system.CSCSymbolIntro)
    - [CSCSymbolList](#biss.api.v1.system.CSCSymbolList)
    - [CSCSystemConfig](#biss.api.v1.system.CSCSystemConfig)
    - [CSCTickerInfo](#biss.api.v1.system.CSCTickerInfo)
    - [CSCTickerList](#biss.api.v1.system.CSCTickerList)
    - [ClientApiMeta](#biss.api.v1.system.ClientApiMeta)
    - [ClientConfig](#biss.api.v1.system.ClientConfig)
    - [ClientIpLog](#biss.api.v1.system.ClientIpLog)
    - [ClientSession](#biss.api.v1.system.ClientSession)
    - [IEOInfo](#biss.api.v1.system.IEOInfo)
    - [IEOInfoReq](#biss.api.v1.system.IEOInfoReq)
    - [IEOInfoResp](#biss.api.v1.system.IEOInfoResp)
    - [IEORoundInfo](#biss.api.v1.system.IEORoundInfo)
    - [LinkedImage](#biss.api.v1.system.LinkedImage)
    - [MarketInfo](#biss.api.v1.system.MarketInfo)
    - [MarketList](#biss.api.v1.system.MarketList)
    - [SymbolInfo](#biss.api.v1.system.SymbolInfo)
    - [SymbolIntroReq](#biss.api.v1.system.SymbolIntroReq)
    - [SymbolIntroResp](#biss.api.v1.system.SymbolIntroResp)
    - [SymbolList](#biss.api.v1.system.SymbolList)
    - [SystemConfig](#biss.api.v1.system.SystemConfig)
    - [TickerInfo](#biss.api.v1.system.TickerInfo)
    - [TickerList](#biss.api.v1.system.TickerList)
  
    - [ClientLanguage](#biss.api.v1.system.ClientLanguage)
    - [TickerStatus](#biss.api.v1.system.TickerStatus)
  
  
    - [System](#biss.api.v1.system.System)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/system.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/system.proto



<a name="biss.api.v1.system.AnnouncementInfo"></a>

### AnnouncementInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| name | [string](#string) |  |  |
| url | [string](#string) |  |  |






<a name="biss.api.v1.system.AppVersion"></a>

### AppVersion



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| platform | [biss.common.Platform](#biss.common.Platform) |  | 平台 |
| version_num | [uint32](#uint32) |  | 最新版本版本号 |
| version_type | [bool](#bool) |  | 是否要强制升级 |
| update_info | [string](#string) |  | 版本更新文案 |
| update_time | [uint64](#uint64) |  | 发布时间 |
| download_url | [string](#string) |  | 新版本下载地址 |
| app_size | [string](#string) |  | app文件大小 |
| app_md5 | [string](#string) |  | app文件MD5值 |






<a name="biss.api.v1.system.AppVersionResp"></a>

### AppVersionResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| versions | [AppVersionResp.VersionsEntry](#biss.api.v1.system.AppVersionResp.VersionsEntry) | repeated | key为platform枚举值 |






<a name="biss.api.v1.system.AppVersionResp.VersionsEntry"></a>

### AppVersionResp.VersionsEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [int32](#int32) |  |  |
| value | [AppVersion](#biss.api.v1.system.AppVersion) |  |  |






<a name="biss.api.v1.system.BannerConfig"></a>

### BannerConfig



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| hero | [BannerConfig.HeroBannerConfig](#biss.api.v1.system.BannerConfig.HeroBannerConfig) |  | 首页大 banner |
| events | [LinkedImage](#biss.api.v1.system.LinkedImage) | repeated | 首页小 banner |
| bissups | [LinkedImage](#biss.api.v1.system.LinkedImage) | repeated | BISS UP banner |






<a name="biss.api.v1.system.BannerConfig.HeroBannerConfig"></a>

### BannerConfig.HeroBannerConfig







<a name="biss.api.v1.system.CSCMarketInfo"></a>

### CSCMarketInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| market | [string](#string) |  |  |
| priority | [uint32](#uint32) |  | 优先级, 排序使用 |
| min_market_buy_amount | [string](#string) |  | 最小市价买单金额 |






<a name="biss.api.v1.system.CSCMarketList"></a>

### CSCMarketList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| markets | [CSCMarketInfo](#biss.api.v1.system.CSCMarketInfo) | repeated |  |






<a name="biss.api.v1.system.CSCSymbolInfo"></a>

### CSCSymbolInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| priority | [uint32](#uint32) |  | 优先级, 排序使用 |
| intros | [CSCSymbolInfo.IntrosEntry](#biss.api.v1.system.CSCSymbolInfo.IntrosEntry) | repeated | 币种简介,key:语言 |






<a name="biss.api.v1.system.CSCSymbolInfo.IntrosEntry"></a>

### CSCSymbolInfo.IntrosEntry



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| key | [int32](#int32) |  |  |
| value | [CSCSymbolIntro](#biss.api.v1.system.CSCSymbolIntro) |  |  |






<a name="biss.api.v1.system.CSCSymbolIntro"></a>

### CSCSymbolIntro
币股system config


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| language | [biss.common.Lang](#biss.common.Lang) |  |  |
| introduction | [string](#string) |  | 介绍 |
| url | [string](#string) |  | 链接 |
| name | [string](#string) |  | 标的名称 |






<a name="biss.api.v1.system.CSCSymbolList"></a>

### CSCSymbolList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbols | [CSCSymbolInfo](#biss.api.v1.system.CSCSymbolInfo) | repeated |  |






<a name="biss.api.v1.system.CSCSystemConfig"></a>

### CSCSystemConfig



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbols | [CSCSymbolInfo](#biss.api.v1.system.CSCSymbolInfo) | repeated |  |
| tickers | [CSCTickerInfo](#biss.api.v1.system.CSCTickerInfo) | repeated |  |
| markets | [CSCMarketInfo](#biss.api.v1.system.CSCMarketInfo) | repeated |  |






<a name="biss.api.v1.system.CSCTickerInfo"></a>

### CSCTickerInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| market | [string](#string) |  |  |
| priority | [uint32](#uint32) |  | 优先级, 排序使用 |
| show_in_home | [bool](#bool) |  | 是否展示在首页 |
| min_trade_price | [string](#string) |  | 最小交易价格 |
| min_trade_qty | [string](#string) |  | 最小交易数量 |
| taker_fee | [biss.common.Fee](#biss.common.Fee) |  | Taker 费率 |
| maker_fee | [biss.common.Fee](#biss.common.Fee) |  | Maker 费率 |
| depth_groups | [string](#string) | repeated | 盘口合并深度 |






<a name="biss.api.v1.system.CSCTickerList"></a>

### CSCTickerList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tickers | [CSCTickerInfo](#biss.api.v1.system.CSCTickerInfo) | repeated |  |






<a name="biss.api.v1.system.ClientApiMeta"></a>

### ClientApiMeta



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| mesg_id | [uint32](#uint32) |  |  |
| ts | [uint32](#uint32) |  |  |
| nonce | [uint32](#uint32) |  |  |
| lang | [biss.common.Lang](#biss.common.Lang) |  |  |
| timezone | [biss.common.TimeZone](#biss.common.TimeZone) |  |  |
| platform | [biss.common.Platform](#biss.common.Platform) |  |  |
| client_ip | [string](#string) |  |  |
| brand | [string](#string) |  |  |
| hardware_version | [uint32](#uint32) |  |  |
| system_version | [uint32](#uint32) |  |  |
| software_version | [uint32](#uint32) |  |  |
| session | [bytes](#bytes) |  |  |






<a name="biss.api.v1.system.ClientConfig"></a>

### ClientConfig



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| country | [biss.common.Country](#biss.common.Country) |  |  |
| banners | [BannerConfig](#biss.api.v1.system.BannerConfig) |  | 首页 Banner |
| poster_image | [string](#string) |  | 分享海报 |
| announcements | [AnnouncementInfo](#biss.api.v1.system.AnnouncementInfo) | repeated | 公告 |






<a name="biss.api.v1.system.ClientIpLog"></a>

### ClientIpLog



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| uid | [uint64](#uint64) |  |  |
| client_ip | [string](#string) |  |  |
| country | [string](#string) |  |  |
| city | [string](#string) |  |  |
| req_type | [string](#string) |  |  |
| timezone | [biss.common.TimeZone](#biss.common.TimeZone) |  |  |






<a name="biss.api.v1.system.ClientSession"></a>

### ClientSession



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| uid | [uint64](#uint64) |  |  |
| key_ver | [uint32](#uint32) |  |  |
| sig_l1 | [bytes](#bytes) |  |  |
| sig_l2 | [bytes](#bytes) |  |  |






<a name="biss.api.v1.system.IEOInfo"></a>

### IEOInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| market | [string](#string) |  |  |






<a name="biss.api.v1.system.IEOInfoReq"></a>

### IEOInfoReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| market | [string](#string) |  |  |






<a name="biss.api.v1.system.IEOInfoResp"></a>

### IEOInfoResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| market | [string](#string) |  |  |
| rounds | [uint32](#uint32) |  | IEO的总轮数 |
| ieo_rounds | [IEORoundInfo](#biss.api.v1.system.IEORoundInfo) | repeated | 轮次信息 |
| server_ts | [uint64](#uint64) |  | 服务器当前时间时间戳(毫秒) |
| ticker_listed_ts | [uint64](#uint64) |  | 标的正式交易时间戳(毫秒) |
| current_round | [uint32](#uint32) |  | 当前轮次(不在轮次中值为0) |
| next_round | [uint32](#uint32) |  | 下一轮轮次(没有下一轮值为0) |






<a name="biss.api.v1.system.IEORoundInfo"></a>

### IEORoundInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| no | [uint32](#uint32) |  | 轮次 |
| is_over | [bool](#bool) |  | 本轮秒杀是否被抢光 |
| start_time | [uint64](#uint64) |  | 本轮秒杀开始时间 |
| finish_time | [uint64](#uint64) |  | 本轮秒杀结束时间 |






<a name="biss.api.v1.system.LinkedImage"></a>

### LinkedImage



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| image | [string](#string) |  | 图片 URL |
| url | [string](#string) |  | 跳转 URL |






<a name="biss.api.v1.system.MarketInfo"></a>

### MarketInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| market | [string](#string) |  |  |
| priority | [uint32](#uint32) |  | 优先级, 排序使用 |
| min_market_buy_amount | [string](#string) |  | 最小市价买单金额 |






<a name="biss.api.v1.system.MarketList"></a>

### MarketList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| markets | [MarketInfo](#biss.api.v1.system.MarketInfo) | repeated |  |






<a name="biss.api.v1.system.SymbolInfo"></a>

### SymbolInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| priority | [uint32](#uint32) |  | 优先级, 排序使用 |
| board | [biss.common.trade.Board](#biss.common.trade.Board) |  | 板块 |
| category | [biss.common.trade.Category](#biss.common.trade.Category) |  | 类型 |
| sub_category | [biss.common.trade.SubCategory](#biss.common.trade.SubCategory) |  | 类型 |
| min_withdraw_qty | [string](#string) |  | 最小提币数量 |
| min_deposit_qty | [string](#string) |  | 最小充值数量 |
| withdraw_quota | [string](#string) |  | 提币限制 |
| confirm_blocks | [uint32](#uint32) |  | 确认到账区块数量 |
| withdraw_blocks | [uint32](#uint32) |  | 确认可提币区块数量 |
| withdraw_fee | [biss.common.Fee](#biss.common.Fee) |  | 提现费率 |
| withdraw_enable | [bool](#bool) |  | 允许提现 |
| deposit_enable | [bool](#bool) |  | 允许充值 |
| icon_url | [string](#string) |  | ICON 链接 |
| name | [string](#string) |  | 多语言相关数据(根据header.Lang)

标的名称 |
| introduction | [string](#string) |  | 币种简介 |
| url | [string](#string) |  | 币种简介链接 |






<a name="biss.api.v1.system.SymbolIntroReq"></a>

### SymbolIntroReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| language | [ClientLanguage](#biss.api.v1.system.ClientLanguage) |  |  |






<a name="biss.api.v1.system.SymbolIntroResp"></a>

### SymbolIntroResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| introduction | [string](#string) |  |  |
| url | [string](#string) |  |  |






<a name="biss.api.v1.system.SymbolList"></a>

### SymbolList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbols | [SymbolInfo](#biss.api.v1.system.SymbolInfo) | repeated |  |






<a name="biss.api.v1.system.SystemConfig"></a>

### SystemConfig



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbols | [SymbolInfo](#biss.api.v1.system.SymbolInfo) | repeated |  |
| tickers | [TickerInfo](#biss.api.v1.system.TickerInfo) | repeated |  |
| markets | [MarketInfo](#biss.api.v1.system.MarketInfo) | repeated |  |
| ieos | [IEOInfo](#biss.api.v1.system.IEOInfo) | repeated |  |






<a name="biss.api.v1.system.TickerInfo"></a>

### TickerInfo



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  |  |
| market | [string](#string) |  |  |
| priority | [uint32](#uint32) |  | 优先级, 排序使用 |
| show_in_home | [bool](#bool) |  | 是否展示在首页 |
| status | [TickerStatus](#biss.api.v1.system.TickerStatus) |  | 标的状态 |
| min_trade_price | [string](#string) |  | 最小交易价格 |
| min_trade_qty | [string](#string) |  | 最小交易数量 |
| taker_fee | [biss.common.Fee](#biss.common.Fee) |  | Taker 费率 |
| maker_fee | [biss.common.Fee](#biss.common.Fee) |  | Maker 费率 |
| depth_groups | [string](#string) | repeated | 盘口合并深度 |
| maintaining_start_ts | [uint64](#uint64) |  | 维护开始时间(维护时间不可交易) |
| maintaining_finish_ts | [uint64](#uint64) |  | 维护结束时间 |
| listed_ts | [uint64](#uint64) |  | 上线时间 |
| unlisted_ts | [uint64](#uint64) |  | 下线时间 |
| trade_price_precision | [string](#string) |  | 交易价格精度 |
| trade_qty_precision | [string](#string) |  | 交易数量精度 |






<a name="biss.api.v1.system.TickerList"></a>

### TickerList



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tickers | [TickerInfo](#biss.api.v1.system.TickerInfo) | repeated |  |





 


<a name="biss.api.v1.system.ClientLanguage"></a>

### ClientLanguage


| Name | Number | Description |
| ---- | ------ | ----------- |
| CL_NONE | 0 |  |
| CL_CH | 1 |  |
| CL_EN | 2 |  |



<a name="biss.api.v1.system.TickerStatus"></a>

### TickerStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| TS_NONE | 0 |  |
| TS_PRELISTED | 1 |  |
| TS_LISTED | 2 | 已上线 |
| TS_UNLISTED | 3 | 已下线 |
| TS_SUSPENDED | 4 |  |
| TS_PREIEO | 5 | 预IEO |
| TS_IEO | 6 | IEO进行中 |


 

 


<a name="biss.api.v1.system.System"></a>

### System


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| GetClientConfig | [.biss.common.Empty](#biss.common.Empty) | [ClientConfig](#biss.api.v1.system.ClientConfig) |  |
| GetSymbolConfig | [.biss.common.Empty](#biss.common.Empty) | [SymbolList](#biss.api.v1.system.SymbolList) |  |
| GetTickerConfig | [.biss.common.Empty](#biss.common.Empty) | [TickerList](#biss.api.v1.system.TickerList) |  |
| GetMarketConfig | [.biss.common.Empty](#biss.common.Empty) | [MarketList](#biss.api.v1.system.MarketList) |  |
| GetSystemConfig | [.biss.common.Empty](#biss.common.Empty) | [SystemConfig](#biss.api.v1.system.SystemConfig) |  |
| GetSymbolIntroduction | [SymbolIntroReq](#biss.api.v1.system.SymbolIntroReq) | [SymbolIntroResp](#biss.api.v1.system.SymbolIntroResp) |  |
| GetCSCSymbolConfig | [.biss.common.Empty](#biss.common.Empty) | [CSCSymbolList](#biss.api.v1.system.CSCSymbolList) |  |
| GetCSCTickerConfig | [.biss.common.Empty](#biss.common.Empty) | [CSCTickerList](#biss.api.v1.system.CSCTickerList) |  |
| GetCSCMarketConfig | [.biss.common.Empty](#biss.common.Empty) | [CSCMarketList](#biss.api.v1.system.CSCMarketList) |  |
| GetCSCSystemConfig | [.biss.common.Empty](#biss.common.Empty) | [CSCSystemConfig](#biss.api.v1.system.CSCSystemConfig) |  |
| GetIEOInfoConfig | [IEOInfoReq](#biss.api.v1.system.IEOInfoReq) | [IEOInfoResp](#biss.api.v1.system.IEOInfoResp) | 获取IEO信息 |
| GetAppVersion | [.biss.common.Empty](#biss.common.Empty) | [AppVersionResp](#biss.api.v1.system.AppVersionResp) | 获取APP的最新版本信息 |

 



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

